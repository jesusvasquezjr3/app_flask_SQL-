# 📝 Flask y PostgreSQL con Supabase

Este es un proyecto de ejemplo que demuestra cómo construir una aplicación web simple con **Flask** que se conecta a una base de datos **PostgreSQL** alojada en **Supabase**. La aplicación permite agregar y listar usuarios, mostrando una integración básica de backend y base de datos.

## 📂 Estructura del Proyecto

El proyecto sigue una organización modular para separar la lógica, las plantillas y los archivos estáticos.

```
app_flask_SQL-/
├── app.py
├── models.py
├── routes.py
├── config.py
├── templates/
│   └── usuarios.html
├── static/
├── requirements.txt
└── .gitignore
```

  * **`app.py`**: Archivo principal que ejecuta la aplicación.
  * **`models.py`**: Define los modelos de la base de datos para SQLAlchemy.
  * **`routes.py`**: Contiene las rutas y la lógica de las vistas.
  * **`config.py`**: Almacena la configuración de la aplicación, como la cadena de conexión a la base de datos.

## 🚀 Instalación y Configuración

Sigue estos pasos para poner en marcha el proyecto en tu entorno local.

1.  **Clona el repositorio** en tu computadora.
    ```bash
    git clone https://github.com/jesusvasquezjr3/app_flask_SQL-
    cd app_flask_SQL-
    ```
2.  **Crea y activa un entorno virtual**.
    ```bash
    # Crear el entorno virtual
    python -m venv venv

    # Activar en Windows
    .\venv\Scripts\activate

    # Activar en macOS/Linux
    source venv/bin/activate
    ```
3.  **Instala las dependencias** usando el archivo `requirements.txt`.
    ```bash
    pip install -r requirements.txt
    ```
4.  **Configura la Base de Datos Supabase**.

      ![SupabaseGIF](static/supabase.gif)
    ***Figura 1.** Table Editor en **Supabase***
      
      * Ve a tu panel de **Supabase** y crea un nuevo proyecto.
      * Dirígete a **Project Settings \> Database**.
      * Encuentra tu **Connection string** (URI) y cópiala.
      * Abre el archivo `config.py` y reemplaza el valor de `SQLALCHEMY_DATABASE_URI` con la URI que copiaste.
        ```python
        # config.py
        class Config:
            # Pega aquí tu URI de conexión de Supabase
            SQLALCHEMY_DATABASE_URI = 'postgresql://user:password@host:port/database'
            SQLALCHEMY_TRACK_MODIFICATIONS = False
        ```

## ▶️ Ejecutar la Aplicación

Con el entorno virtual activado y la configuración lista, inicia el servidor de Flask.

```bash
python app.py
```

La aplicación creará las tablas de la base de datos automáticamente al iniciar y estará disponible en `http://127.0.0.1:5000`.

## Resultados

![Tabla](static/supabase.png)
***Figura 2.** Base de Datos **Supabase***

![Visualizacion](static/usuarios.png)
***Figura 3.** Visualización de Usuarios*


### Endpoints Disponibles

  * **Agregar un usuario**: `http://127.0.0.1:5000/add_user/<nombre>/<email>`
  * **Listar usuarios**: `http://127.0.0.1:5000/usuarios`
