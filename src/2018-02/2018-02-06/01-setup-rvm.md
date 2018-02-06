# setup -rvm

## curl:
```conf
-d --data 使用POST方法， -d 后面的是post的数据
-s --silent 静默模式，就是不显示错误和进度, 如果没有指定-d(或者其他方式) 默认为GET
```

## install rvm:
```shell
curl -sSL https://get.rvm.io | bash -s stable
```

## if you have rmv, update to statble:
```shell
rvm get stable
```

## check if installed sucess:
```conf
$ rvm -v
rvm 1.29.3 (latest) by Michal Papis, Piotr Kuczynski, Wayne E. Seguin [https://rvm.io]
```