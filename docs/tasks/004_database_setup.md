# Tarea 004: Configuración de Base de Datos (Supabase)

- **Descripción**: Configurar la conexión con Supabase, definir el esquema inicial de la base de datos y desarrollar el servicio de acceso a datos `data_supabase.py`.
- **Criterios de Aceptación**:
  - Conexión con Supabase establecida y verificada mediante un endpoint de prueba.
  - El archivo `data_supabase.py` contiene la clase `SupabaseService` con métodos para operaciones CRUD básicas.
  - El esquema de base de datos inicial (tablas para usuarios, farmacias, productos) está definido y creado en Supabase.
  - Se implementa el patrón Singleton para la instancia de `SupabaseService`.
- **Archivos Afectados**:
  - `app/data_supabase.py`
  - `docs/database_schema.md` (documento para definir el esquema)
- **Dependencias**: `003_core_backend.md`
- **Tiempo Estimado**: 6 horas.
- **Notas Técnicas**:
  - `SupabaseService` debe manejar la inicialización del cliente y la reutilización de la conexión.
  - Los métodos deben incluir `insert`, `select`, `update`, `delete`, y `call_rpc`.
  - El esquema inicial debe reflejar los requerimientos del PRD para las entidades principales.
  - Se creará un blueprint en `data_supabase.py` para exponer un endpoint de test de conexión (`/api/supabase/test`). 