# `rm` 移除文件

## 说明

**r**e**m**ove，移除的含义，使用这个命令可以删除文件或者目录。

### 语法

```shell
rm [参数] 文件名...
```

## 参数

### 无需询问，直接删除 - 参数 f

如果我们只是使用 rm 命令（不加参数）删除某文件的话，每次都会询问是否删除，如果我们需要强制删除，就需要**参数 `f`**，force（强制）的含义，即使原档案属性设为唯读，亦直接删除，无需逐一确认。

```shell
$ tree # 当前目录下的文件结构
.
├── hello
└── tests
    └── meow

$ rm tests/meow
是否删除 一般文件 "meow"? y # 此时需要加 y

$ rm -f tests/meow

$ tree # 成功删除
.
├── hello
└── tests
```

### 递归删除目录下子目录及其文件 - 参数 r

有时候我们需要把目录下面完全清空，需要用到**参数 `r`**，r（递归）的含义，将目录及以下之档案亦逐一删除。

```shell
$ tree # 当前目录下的文件结构
.
├── hello
└── tests
    ├── meow
    └── tests2
        └── meow2
    
$ rm tests # 尝试删除 tests 目录
rm: 无法删除'tests': 是一个目录

$ rm -r tests # 加参数 r

$ tree # 成功删除
.
└── hello
```
