# Acceso-a-Base-de-Datos

Rushell Vanessa Zavalaga Orozco, rzavalaga@unsa.edu.pe

Objetivo: Entender conceptos relacionados a Java (JSP, Servlet, Javabean) y Base de Datos

En este laboratorio, crearemos una aplicación web que administra una colección de usuarios con las funcioalidade básicas de: listar, insertar, actualizar, eliminar (u operaciones de CRUD:  Create, Update, Read and Delete ).

Pre-requisitos: Eclipse, Tomcat, Java, JSTL, MySQL

Actividades:

    a. Crear un Proyecto Web Java en base a el siguiente Tutorial https://www.javaguides.net/2019/03/jsp-servlet-jdbc-mysql-crud-example-tutorial.html
        • Crear un esquema de Base Datos
        • Crear Servlets
        • Crear páginas JSP
        • Conectarse a MySQL
        • Actualizar la base de datos
        • Consultar la base de datos

    b. Ejecutar el Proyecto

Entregable: 
Repositorio Github conteniendo el proyecto
Evidencias de la ejecución del proyecto - prints de pantallas

Observación: Pueden usar este otro tutorial tambien https://www.codejava.net/coding/jsp-servlet-jdbc-mysql-create-read-update-delete-crud-example

DataSource: Otra forma de accesar una base de datos en java

                    public class Conexion {
                     private static BasicDataSource dataSource = null;

                     private static DataSource getDataSource() {
                      if (dataSource == null) {
                       dataSource = new BasicDataSource();
                       dataSource.setDriverClassName("com.mysql.cj.jdbc.Driver");
                       dataSource.setUsername("root");
                       dataSource.setPassword("root");
                       dataSource.setUrl("jdbc:mysql://localhost:3306/crud?useTimezone=true&serverTimezone=UTC");
                       dataSource.setInitialSize(20);
                       dataSource.setMaxIdle(15);
                       dataSource.setMaxTotal(20);
                       dataSource.setMaxWaitMillis(5000);
                      }
                      return dataSource;
                     }

                     public static Connection getConnection() throws SQLException {
                      return getDataSource().getConnection();
                     }
                    }
