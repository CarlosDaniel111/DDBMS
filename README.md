# 🗄️ Sistema Gestor de Base de Datos Distribuidas

Este proyecto implementa un **Sistema Gestor de Base de Datos Distribuidas (DDBMS)** en **Java**, que permite la interacción coordinada entre tres tipos de bases de datos: **MongoDB, SQL y Neo4j**.  

El sistema sigue la arquitectura **MVC (Modelo-Vista-Controlador)** y asegura la **consistencia de las transacciones distribuidas** mediante la implementación del **protocolo de Commit en 2 Fases (Two-Phase Commit, 2PC)**.

---

## 🚀 Tecnologías utilizadas
- **Lenguaje:** Java  
- **Bases de datos:**
  - 🟢 MongoDB  
  - 🐬 MySQL
  - 🔵 Neo4j
- **Arquitectura:** MVC  
- **Gestión de transacciones:** Protocolo de Commit en 2 Fases (2PC)  

---

## ✨ Funcionalidades principales
- 🔗 **Conexión con múltiples bases de datos** (NoSQL, SQL y grafos).  
- 📝 **Ejecución de operaciones CRUD distribuidas**.  
- 🔒 **Consistencia asegurada con el protocolo 2PC** en transacciones distribuidas.  
- 🧩 **Arquitectura MVC** para separación de responsabilidades.  
- 📊 **Consultas híbridas** entre diferentes motores de base de datos.  

---

## ⚙️ Instalación y ejecución

### 1. Clonar el repositorio
```bash
git clone https://github.com/tu-usuario/gestor-bd-distribuidas.git
cd gestor-bd-distribuidas
```

### 2. Configuración de las bases de datos
- Crear las instancias de:
  - **MongoDB**
  - **MySQL / PostgreSQL**
  - **Neo4j**
- Configurar credenciales y puertos en el archivo `config.properties`:
```properties
# MongoDB
MONGO_URI=mongodb://localhost:27017
MONGO_DB=distribuidas

# SQL
SQL_URL=jdbc:mysql://localhost:3306/distribuidas
SQL_USER=root
SQL_PASSWORD=tu_password

# Neo4j
NEO4J_URI=bolt://localhost:7687
NEO4J_USER=neo4j
NEO4J_PASSWORD=tu_password
```

### 3. Compilar y ejecutar
```bash
javac -d bin src/**/*.java
java -cp bin Main
```

---

## 📌 Uso
1. Ejecutar el sistema desde la clase `Main`.  
2. Seleccionar el tipo de operación (consulta, inserción, actualización, eliminación).  
3. Observar cómo se distribuye la transacción entre las bases de datos.  
4. En caso de fallo, el **protocolo 2PC** asegura **rollback** en todas las bases para mantener consistencia.  

---

## 📐 Arquitectura MVC
- **Modelo:** Gestión de conexión y operaciones sobre cada base de datos.  
- **Vista:** Interfaz simple (consola o GUI) para interacción del usuario.  
- **Controlador:** Coordina la ejecución de transacciones y aplica el protocolo 2PC.  
