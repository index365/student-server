这是一个基于 Spring Boot 的学生信息管理系统后端项目。以下是这个项目的功能和结构：

1. 技术栈：

- Spring Boot 3.5.0

- Spring Data JPA

- MySQL 数据库

- Maven 构建工具

- Lombok 用于简化代码

2. 主要功能：

这是一个学生信息管理系统的后端 API，提供以下功能：

- 学生信息的增删改查（CRUD）操作

- 支持按学号查询学生信息

- 支持按 ID 查询学生信息

- 支持获取所有学生信息列表

3. 项目结构：

src/main/java/com/example/student/
├── controller/          # 控制器层，处理 HTTP 请求
├── service/            # 服务层，处理业务逻辑
├── repository/         # 数据访问层，与数据库交互
├── entity/            # 实体类，定义数据模型
└── StudentServerApplication.java  # 应用程序入口

4. 核心功能模块：

a) 学生实体（Student）：

- 包含以下字段：

- id：主键

- name：学生姓名

- studentNumber：学号（唯一）

- phone：电话号码

- major：专业

b) API 接口（StudentController）：

- POST /api/students - 创建新学生

- GET /api/students - 获取所有学生列表

- GET /api/students/{id} - 根据 ID 获取学生信息

- GET /api/students/number/{studentNumber} - 根据学号获取学生信息

- PUT /api/students/{id} - 更新学生信息

- DELETE /api/students/{id} - 删除学生信息

5. 数据库配置：

- 使用 MySQL 数据库

- 数据库名：student

- 自动更新表结构（spring.jpa.hibernate.ddl-auto=update）

- 显示 SQL 语句（spring.jpa.show-sql=true）

6. 特点：

- 采用 RESTful API 设计风格

- 支持跨域请求（@CrossOrigin）

- 使用 JPA 进行数据库操作

- 采用分层架构，代码结构清晰

- 使用 Lombok 简化代码

7. 运行环境：

- Java 24

- MySQL 数据库

- 默认运行在 8080 端口

8. student数据库建表语句：
CREATE TABLE students (
  id BIGINT NOT NULL AUTO_INCREMENT,
  major VARCHAR(255) NOT NULL,
  name VARCHAR(255) NOT NULL,
  phone VARCHAR(255) NOT NULL,
  student_number VARCHAR(255) NOT NULL,
  PRIMARY KEY (id),
  UNIQUE KEY (student_number)
);
