---
layout: post
title: "CppEmployeeSystem：简单的员工管理系统示例"
date: 2025-02-22 13:39:28 +0900
categories: jekyll update
---

# CppEmployeeSystem — 简单的的员工管理系统示例

这是一个用 C++ 写的简单员工管理系统，演示了怎么连接 PostgreSQL 数据库，做增删改查操作。

## 主要功能

- 添加新员工
- 查看所有员工
- 通过员工ID查找员工
- 修改员工信息
- 删除员工

## 需要准备的环境

- 支持 C++26 的编译器（建议用 GCC 13 或更高）
- PostgreSQL 数据库
- libpqxx 库（PostgreSQL C++客户端库）
- CMake 工具（版本 3.10 或更高）

## 怎么编译运行？

1. 先把项目克隆到本地：

```bash
git clone https://github.com/你的用户名/CppEmployeeSystem.git
cd CppEmployeeSystem

    创建构建目录，生成编译文件并编译：

mkdir build
cd build
cmake ..
make

    运行程序：

./CppEmployeeSystem

配置说明

程序的数据库连接信息放在根目录的 config.json 文件里，格式像这样：

{
  "connection_string": "host=localhost port=5432 dbname=employees user=postgres password=你的密码"
}

把 "你的密码" 改成你自己的 PostgreSQL 数据库密码。
代码接口介绍

    添加员工

service.addEmployee(Employee(...));

查看所有员工

auto list = service.getAllEmployees();

根据 ID 查找员工

auto emp = service.getEmployeeById(id);

修改员工信息

service.updateEmployee(Employee(...));

删除员工

    service.deleteEmployee(id);

许可证

本项目使用 BSD 2-Clause 许可证，欢迎大家自由使用和修改。
