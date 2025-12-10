# 🧩 OrionTek - Clientes Control API

API REST desarrollada en **Java con Spring Boot**, utilizando **CQRS** y **PostgreSQL** para la gestión de clientes y direcciones.

---

## 🛠️ Stack Tecnológico

<p align="center">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" width="60" alt="Java"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/spring/spring-original.svg" width="60" alt="Spring Boot"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original.svg" width="60" alt="PostgreSQL"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/maven/maven-original.svg" width="60" alt="Maven"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original.svg" width="60" alt="Git"/>
</p>

| Tecnología   | Uso en el proyecto                         |
|-------------|----------------------------------------------|
| Java         | Lenguaje principal del backend              |
| Spring Boot  | Framework para crear la API REST            |
| PostgreSQL   | Base de datos relacional                    |
| Maven        | Gestión de dependencias y build             |
| Git / GitHub | Control de versiones                        |

---

## 📊 Diagrama de la Base de Datos

## 📊 Modelo Relacional de la Base de Datos

```text
┌──────────────────────┐
│       CLIENT         │
├──────────────────────┤
│ id (PK)              │
│ name                 │
│ email                │
├──────────────────────┤
│ created_at           │
└─────────┬────────────┘
          │ 1
          │
          │ N
┌─────────▼────────────┐
│      ADDRESS         │
├──────────────────────┤
│ id (PK)              │
│ street               │
│ city                 │
│ country              │
│ client_id (FK)       │
├──────────────────────┤
│ created_at           │
└──────────────────────┘

