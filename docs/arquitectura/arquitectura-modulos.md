# Documentación de Módulos Especializados

Este documento detalla la estructura, convenciones y plantillas para la creación de Módulos Especializados dentro de la arquitectura del proyecto.

---

## 6.1 Estructura de Módulos

Los módulos especializados siguen una estructura consistente que permite la separación clara de responsabilidades por dominio de negocio.

#### Estructura Base de un Módulo

```
routes/
└── module_name/
    ├── web.py                # 🌐 Rutas web principales
    ├── api_feature_1.py      # 🌐 API de feature 1
    ├── api_feature_2.py      # 🌐 API de feature 2
    └── api_feature_n.py      # 🌐 API de feature N
```

#### Registro de Blueprints (`routes_module_name.py`)

```python
# Blueprint principal para páginas web
module_bp = Blueprint('module_name', __name__, url_prefix='/module_name')
module_bp.register_blueprint(module_web_bp)

# Blueprint para APIs
module_api_bp = Blueprint('module_name_api', __name__, url_prefix='/api/module_name')
module_api_bp.register_blueprint(feature_1_api_bp, url_prefix='/feature_1')
module_api_bp.register_blueprint(feature_2_api_bp, url_prefix='/feature_2')
module_api_bp.register_blueprint(feature_n_api_bp, url_prefix='/feature_n')

def register_module_blueprints(app):
    """Register all module blueprints with the Flask app."""
    app.register_blueprint(module_bp)
    app.register_blueprint(module_api_bp)
```

---

## 6.2 Convenciones de Módulos

#### Rutas Web (`routes/module_name/web.py`)
- Páginas principales del módulo
- Renderizado de templates
- Navegación entre vistas
- Formularios web

#### APIs de Features (`routes/module_name/api_feature_*.py`)
- Endpoints REST específicos por feature
- Operaciones CRUD
- Validación de datos
- Respuestas JSON estructuradas

---

## 6.3 Plantilla de Módulo

#### Archivo de Registro (`routes_module_template.py`)
```python
from flask import Blueprint
from app.routes.module_template.web import module_template_web_bp
from app.routes.module_template.api_feature_1 import feature_1_api_bp
from app.routes.module_template.api_feature_2 import feature_2_api_bp

# Blueprint principal para páginas web
module_template_bp = Blueprint('module_template', __name__, url_prefix='/module_template')
module_template_bp.register_blueprint(module_template_web_bp)

# Blueprint para APIs
module_template_api_bp = Blueprint('module_template_api', __name__, url_prefix='/api/module_template')
module_template_api_bp.register_blueprint(feature_1_api_bp, url_prefix='/feature_1')
module_template_api_bp.register_blueprint(feature_2_api_bp, url_prefix='/feature_2')

def register_module_template_blueprints(app):
    """Register all module template blueprints with the Flask app."""
    app.register_blueprint(module_template_bp)
    app.register_blueprint(module_template_api_bp)
```

#### Rutas Web (`routes/module_template/web.py`)
```python
from flask import Blueprint, render_template, request, redirect, url_for
from app.utils_messages import MessageFormatter, Messages
from app.core_logging import get_logger

module_template_web_bp = Blueprint('module_template_web', __name__)
logger = get_logger(__name__)

@module_template_web_bp.route('/')
def index():
    """Dashboard principal del módulo."""
    return render_template('module_template/index.html')

@module_template_web_bp.route('/feature_1')
def feature_1():
    """Vista de feature 1."""
    return render_template('module_template/feature_1.html')

@module_template_web_bp.route('/feature_2')
def feature_2():
    """Vista de feature 2."""
    return render_template('module_template/feature_2.html')
```

#### API de Feature (`routes/module_template/api_feature_1.py`)
```python
from flask import Blueprint, request, jsonify
from app.data_supabase import SupabaseService
from app.utils_messages import MessageFormatter, Messages
from app.core_logging import get_logger

feature_1_api_bp = Blueprint('feature_1_api', __name__)
logger = get_logger(__name__)
supabase_service = SupabaseService()

@feature_1_api_bp.route('/', methods=['GET'])
def get_items():
    """Obtener lista de items."""
    try:
        # Lógica de negocio aquí
        result = supabase_service.select_data('table_name')
        
        if result['success']:
            return jsonify(MessageFormatter.success_response(
                "Items retrieved successfully", 
                result['data']
            ))
        else:
            return jsonify(MessageFormatter.error_response(
                result['message']
            )), 400
            
    except Exception as e:
        logger.error(f"Error getting items: {str(e)}")
        return jsonify(MessageFormatter.error_response(
            Messages.ERROR_GENERAL
        )), 500

@feature_1_api_bp.route('/', methods=['POST'])
def create_item():
    """Crear nuevo item."""
    try:
        data = request.get_json()
        
        # Validación de datos
        if not data:
            return jsonify(MessageFormatter.error_response(
                Messages.ERROR_INVALID_DATA
            )), 400
        
        # Lógica de creación
        result = supabase_service.insert_data('table_name', data)
        
        if result['success']:
            return jsonify(MessageFormatter.success_response(
                Messages.ITEM_CREATED, 
                result['data']
            )), 201
        else:
            return jsonify(MessageFormatter.error_response(
                result['message']
            )), 400
            
    except Exception as e:
        logger.error(f"Error creating item: {str(e)}")
        return jsonify(MessageFormatter.error_response(
            Messages.ERROR_GENERAL
        )), 500

@feature_1_api_bp.route('/<int:item_id>', methods=['PUT'])
def update_item(item_id):
    """Actualizar item existente."""
    try:
        data = request.get_json()
        
        # Validación de datos
        if not data:
            return jsonify(MessageFormatter.error_response(
                Messages.ERROR_INVALID_DATA
            )), 400
        
        # Lógica de actualización
        result = supabase_service.update_data(
            'table_name', 
            data, 
            {'id': item_id}
        )
        
        if result['success']:
            return jsonify(MessageFormatter.success_response(
                Messages.ITEM_UPDATED, 
                result['data']
            ))
        else:
            return jsonify(MessageFormatter.error_response(
                result['message']
            )), 400
            
    except Exception as e:
        logger.error(f"Error updating item {item_id}: {str(e)}")
        return jsonify(MessageFormatter.error_response(
            Messages.ERROR_GENERAL
        )), 500

@feature_1_api_bp.route('/<int:item_id>', methods=['DELETE'])
def delete_item(item_id):
    """Eliminar item."""
    try:
        result = supabase_service.delete_data(
            'table_name', 
            {'id': item_id}
        )
        
        if result['success']:
            return jsonify(MessageFormatter.success_response(
                Messages.ITEM_DELETED
            ))
        else:
            return jsonify(MessageFormatter.error_response(
                result['message']
            )), 400
            
    except Exception as e:
        logger.error(f"Error deleting item {item_id}: {str(e)}")
        return jsonify(MessageFormatter.error_response(
            Messages.ERROR_GENERAL
        )), 500
``` 