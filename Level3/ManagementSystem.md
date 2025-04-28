# 2024-backend-recruit-03-Level3

# **考核说明-呱呱学术管家**

**本考核内容针对学习java的同学设计**

## **项目介绍（场景介绍）**

​		小爪是一名大学生，出于对编程的热爱，选择了计算机专业。小爪上了大学，一直热衷于学习，钻研书籍。所以，到了大一学期下半年，小爪就已经学习大部分技术。但是令小爪头痛的是：学了很多技术但是却没有用武之地，小爪因为是自学且领先了别人一大步，所以它不知道有哪些项目比较适合拿来练手。这个时候，小爪突然想到了前几天为了给下学期选则选修课的教务系统。小爪一直很好奇：为什么教务系统每到选课的时候基本上登不上去，然后是如何保证选课安全的问题。这个时候，小爪的头脑里突然萌生了很多想法：想要实现很多模块（管理员、教师、学生）等有关角色模块.....，但是，小爪发现自己的重点都是在软件设计的学习，而对于代码的具体实现却没有深入。小爪也不灰心，想着把核心功能和一些伴随功能可以实现的前提下，并添加自己的创意（不会脱离教务系统的定义）,并寻找一位可以信任的小伙伴来帮助小爪一起开发，你会是小爪的伙伴吗?

为小爪使用代码实现一个教务系统的后端API，并且利用Java原生API、JavaWeb等知识，完成以下要求：

## **涉及技术关键字**

1. JavaSE相关知识（接口、抽象类、异常处理、多线程等..）
2. JavaWeb
3. Tomcat
4. SQL（采用MYSQL数据库）
5. RESTful API设计规范
6. 接口文档工具(Swagger/Apifox等)

## **角色要求**

| 角色   | 职责说明                                                     |
| ------ | ------------------------------------------------------------ |
| 管理员 | 一般为该系统的负责人员担任，负责教师/学生信息的添加、修改、删除、查询等 |
| 教师   | 负责讲授课程的教师，一般负责添加课程信息、修改课程信息、设置分数比重... |
| 学生   | 该系统的主要用户，一般只具备读功能                           |

## **业务功能要求**

### 一. **基本内容及功能**

#### 1. 登录功能

需要实现完整的登录认证机制,支持以下功能:

1. 实现最基本的账号验证、密码校验要求
2. 实现登录后的令牌分发与校验
3. 权限控制（尽量实现）
4. 登出功能

接口示例:
```http
POST /api/auth/login
Content-Type: application/json

{
  "username": "string",
  "password": "string",
  "role": "ADMIN|TEACHER|STUDENT"
}
```

#### 2. **教师功能**

##### 2.1 课程管理

提供以下API:

1. 添加课程
2. 修改课程信息(可选)
3. 删除课程(可选)
4. 查询课程信息
5. 申请课程状态变更(可选)

课程信息包含:
- 课程名称
- 课程编号(该字段一般由系统生成)
- 适用专业
- 适用年级（大一、大二等）
- 课程性质(必修/选修)
- 是否公开：该课程是否一旦申请通过，就可以供学生选择；若选择隐藏，则不会存储到公开池下
- 课程状态(已提交/审核通过/审核不通过/公开/隐藏)

#### 3. **学生功能**

提供以下API:

1. 查询个人信息
2. 修改个人信息（密码等)
3. 查询课表（每个学生的课表都可能不相同）
4. 选课（选择选修课）

#### 4. **管理员功能**

小爪想体验一下超管的至高无上的权力，于是特地想让你实现一下这个功能，不过没有完全实现也没有关系，能完成上面的已经很棒啦！

**角色作用**：一般是为了管理教务系统所有非管理员账号的添加、删除、查询、管理

**注意事项**：这里的账号管理非账号详细信息的管理，而是针对于账号和状态的管理

**建议**：该模块部分功能为**可选功能**，是否实现该功能取决于对于该项目的规划和时间安排

##### 4.1 教师账号管理

提供以下API:

1. 添加教师账号
2. 批量添加教师账号(可选)
3. 修改教师账号信息(可选)
4. 删除教师账号(可选)
5. 查询教师账号信息

教师账号格式规范:

- 账号格式: 届号(2位) + 院系号(3位) + 添加顺序(4位)
- 例如: 23001001 表示23届001院系第1号教师

##### 4.2 学生账号管理 

提供以下API:

1. 添加学生账号
2. 批量添加学生账号 (可选)
3. 修改学生账号信息(可选)
4. 删除学生账号(可选)
5. 查询学生账号信息

学生账号格式规范:

- 账号格式: 届号(2位) + 院系号(3位) + 专业号(2位) + 班级号(1~2位) + 序号(2位)
- 例如: 2300101101 表示23届001院系01专业1班01号学生

##### 4.3 院系管理

提供以下API:

1. 添加院系
2. 修改院系信息(可选)
3. 删除院系(可选)
4. 查询院系信息

##### 4.4 专业管理

提供以下API:

1. 添加专业
2. 修改专业信息  (可选)
3. 删除专业(可选)
4. 查询专业信息

##### 4.5 权限管理(可选)

提供以下API:

1. 分配教师权限
2. 处理权限申请
3. 处理课程状态变更申请

## **高级功能要求**

1. 底层基于Servlet模拟SpringMvc的调度器，减少Servlet的使用，使“普通类也具备请求处理的能力”
2. 整合Jdbc封装一个模板类，将JDBC的繁琐细节封装起来，对外只保留只需要传入sql语句、参数，返回类型的接口，可以借鉴Spring整合JDBC提供的JdbcTemplate
3. 编写缓存池，在Java内存区域下划分出一块缓存区域（定义缓存池类）；可以参考redis数据库的实现，具体借鉴JSR-107规范
4. 数据库对象的使用，除了使用表之外，还可以使用视图、存储对象、触发器来提高持久化查询的效率

## **技术要求**

1. 遵循RESTful API设计规范
2. 使用Swagger/Apifox等工具编写API文档
3. 在数据库设计方面，请大致浏览一下该考核文档后做出总结
4. 实现统一的异常处理
5. 实现统一的响应格式
6. 合理使用设计模式
7. 代码结构清晰,遵循阿里巴巴Java开发规范

## **项目交付物**

1. 源代码(包含完整的注释)
2. API文档(Swagger/Apifox导出)
3. 项目说明文档(Markdown格式)
   - 项目说明
   - 数据库设计说明
   - 配置说明
   - 使用说明
   - 测试说明
4. 数据库脚本(指定MySQL版本8.0+,可以从找数据库工具导出所有建表语句)

## 其他要求

1. 专注于后端业务逻辑实现,不要求提供前端页面
2. 要求分包分类，切勿一个包一个类写到底！！！
3. 所有接口可通过Postman/Apifox等工具测试
4. 代码注释务必写好。标明每一个方法的作用、变量的作用等等
5. 严禁使用中文拼音或其缩写作为名称。在同一个项目中保持统一的命名规范（建议驼峰式大小写）。命名需要有语义，接近自然语言。尽量少使用临时性命名。可以参照《阿里巴巴Java开发手册》
6. 文件编码统一使用UTF-8。避免在其他人查阅你的代码时无法查看注释

## **可能的帮助**

这里提供**部分**可能对类的定义和建表语句脚本以作示例，自行根据情况修改

### 类的定义：

```java
/**
 * 用户基类
 */
public abstract class BaseUser {
    /** 用户ID */
    private Long id;
    /** 用户名 */
    private String username;
    /** 密码(加密存储) */
    private String password;
    /** 角色 */
    private String role;
    /** 创建时间 */
    private LocalDateTime createTime;
    /** 更新时间 */
    private LocalDateTime updateTime;
    /** 状态(0-正常,1-禁用) */
    private Integer status;
    
    // getter setter 方法省略
}

/**
 * 教师实体类
 */
public class Teacher extends BaseUser {
    /** 教师工号 */
    private String teacherNo;
    /** 所属院系ID */
    private Long departmentId;
    /** 教师姓名 */
    private String name;
    /** 联系电话 */
    private String phone;
    /** 邮箱 */
    private String email;
    
    // getter setter 方法省略
}

/**
 * 课程实体类
 */
public class Course {
    /** 课程ID */
    private Long id;
    /** 课程编号 */
    private String courseNo;
    /** 课程名称 */
    private String courseName;
    /** 授课教师ID */
    private Long teacherId;
    /** 适用专业ID */
    private Long majorId;
    /** 适用年级 */
    private Integer grade;
    /** 课程性质(1-必修,2-选修) */
    private Integer courseType;
    /** 学分 */
    private BigDecimal credit;
    /** 是否公开(0-否,1-是) */
    private Integer isPublic;
    /** 课程状态(1-已提交,2-审核通过,3-审核不通过,4-公开,5-隐藏) */
    private Integer status;
    /** 创建时间 */
    private LocalDateTime createTime;
    /** 更新时间 */
    private LocalDateTime updateTime;
    
    // getter setter 方法省略
}
```

### 建表语句

```sql
-- 创建用户表
CREATE TABLE `t_user` (
  `id` bigint NOT NULL AUTO_INCREMENT COMMENT '主键ID',
  `username` varchar(50) NOT NULL COMMENT '用户名',
  `password` varchar(100) NOT NULL COMMENT '密码',
  `role` varchar(20) NOT NULL COMMENT '角色(ADMIN/TEACHER/STUDENT)',
  `status` tinyint NOT NULL DEFAULT '0' COMMENT '状态(0-正常,1-禁用)',
  `create_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `update_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
  PRIMARY KEY (`id`),
  UNIQUE KEY `uk_username` (`username`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COMMENT='用户表';

-- 创建教师表
CREATE TABLE `t_teacher` (
  `id` bigint NOT NULL AUTO_INCREMENT COMMENT '主键ID',
  `user_id` bigint NOT NULL COMMENT '用户ID',
  `teacher_no` varchar(20) NOT NULL COMMENT '教师工号',
  `department_id` bigint NOT NULL COMMENT '院系ID',
  `name` varchar(50) NOT NULL COMMENT '教师姓名',
  `phone` varchar(20) DEFAULT NULL COMMENT '联系电话',
  `email` varchar(50) DEFAULT NULL COMMENT '邮箱',
  `create_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `update_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
  PRIMARY KEY (`id`),
  UNIQUE KEY `uk_teacher_no` (`teacher_no`),
  KEY `idx_department_id` (`department_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COMMENT='教师表';

-- 创建课程表
CREATE TABLE `t_course` (
  `id` bigint NOT NULL AUTO_INCREMENT COMMENT '主键ID',
  `course_no` varchar(20) NOT NULL COMMENT '课程编号',
  `course_name` varchar(100) NOT NULL COMMENT '课程名称',
  `teacher_id` bigint NOT NULL COMMENT '授课教师ID',
  `major_id` bigint NOT NULL COMMENT '适用专业ID',
  `grade` tinyint NOT NULL COMMENT '适用年级',
  `course_type` tinyint NOT NULL COMMENT '课程性质(1-必修,2-选修)',
  `credit` decimal(3,1) NOT NULL COMMENT '学分',
  `is_public` tinyint NOT NULL DEFAULT '0' COMMENT '是否公开(0-否,1-是)',
  `status` tinyint NOT NULL COMMENT '课程状态(1-已提交,2-审核通过,3-审核不通过,4-公开,5-隐藏)',
  `create_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `update_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
  PRIMARY KEY (`id`),
  UNIQUE KEY `uk_course_no` (`course_no`),
  KEY `idx_teacher_id` (`teacher_id`),
  KEY `idx_major_id` (`major_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COMMENT='课程表';

-- 创建院系表
CREATE TABLE `t_department` (
  `id` bigint NOT NULL AUTO_INCREMENT COMMENT '主键ID',
  `dept_no` varchar(10) NOT NULL COMMENT '院系编号',
  `dept_name` varchar(50) NOT NULL COMMENT '院系名称',
  `create_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `update_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
  PRIMARY KEY (`id`),
  UNIQUE KEY `uk_dept_no` (`dept_no`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COMMENT='院系表';

-- 创建专业表
CREATE TABLE `t_major` (
  `id` bigint NOT NULL AUTO_INCREMENT COMMENT '主键ID',
  `major_no` varchar(10) NOT NULL COMMENT '专业编号',
  `major_name` varchar(50) NOT NULL COMMENT '专业名称',
  `department_id` bigint NOT NULL COMMENT '所属院系ID',
  `create_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `update_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
  PRIMARY KEY (`id`),
  UNIQUE KEY `uk_major_no` (`major_no`),
  KEY `idx_department_id` (`department_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COMMENT='专业表';
```

### 响应格式

```java
/**
 * 统一响应结果
 * @param <T> 响应数据类型
 */
public class Result<T> {
    /** 响应码 */
    private Integer code;
    /** 响应消息 */
    private String message;
    /** 响应数据 */
    private T data;
    /** 响应时间戳 */
    private Long timestamp;
    
    /** 成功响应码 */
    public static final Integer SUCCESS = 200;
    /** 参数错误响应码 */
    public static final Integer PARAM_ERROR = 400;
    /** 未授权响应码 */
    public static final Integer UNAUTHORIZED = 401;
    /** 禁止访问响应码 */
    public static final Integer FORBIDDEN = 403;
    /** 资源不存在响应码 */
    public static final Integer NOT_FOUND = 404;
    /** 服务器错误响应码 */
    public static final Integer ERROR = 500;

    /**
     * 私有构造方法
     */
    private Result() {
        this.timestamp = System.currentTimeMillis();
    }

    /**
     * 成功响应
     */
    public static <T> Result<T> success() {
        Result<T> result = new Result<>();
        result.setCode(SUCCESS);
        result.setMessage("操作成功");
        return result;
    }

    /**
     * 成功响应
     * @param data 响应数据
     */
    public static <T> Result<T> success(T data) {
        Result<T> result = new Result<>();
        result.setCode(SUCCESS);
        result.setMessage("操作成功");
        result.setData(data);
        return result;
    }

    /**
     * 失败响应
     * @param code 错误码
     * @param message 错误信息
     */
    public static <T> Result<T> error(Integer code, String message) {
        Result<T> result = new Result<>();
        result.setCode(code);
        result.setMessage(message);
        return result;
    }

    // getter setter 方法省略
}

/**
 * 分页查询结果
 * @param <T> 数据类型
 */
public class PageResult<T> {
    /** 总记录数 */
    private Long total;
    /** 当前页码 */
    private Integer pageNum;
    /** 每页大小 */
    private Integer pageSize;
    /** 数据列表 */
    private List<T> list;
    
    // getter setter 方法省略
}
```

### 可能的完整请求及响应

```json
POST /api/auth/login

Request:
{
    "username": "teacher001",
    "password": "123456",
    "role": "TEACHER"
}

Response:
{
    "code": 200,
    "message": "登录成功",
    "data": {
        "token": "eyJhbGciOiJIUzI1NiJ9...",
        "userInfo": {
            "id": 1,
            "username": "teacher001",
            "role": "TEACHER",
            "name": "张三",
            "teacherNo": "23001001"
        }
    },
    "timestamp": 1678881234567
}
```

```json
POST /api/teacher/course

Request:
{
    "courseName": "Java程序设计",
    "majorId": 1,
    "grade": 1,
    "courseType": 1,
    "credit": 3.0,
    "isPublic": 1
}

Response:
{
    "code": 200,
    "message": "添加成功",
    "data": {
        "id": 1,
        "courseNo": "CS001",
        "courseName": "Java程序设计"
    },
    "timestamp": 1678881234567
}
```

