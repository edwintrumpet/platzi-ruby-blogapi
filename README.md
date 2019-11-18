# BlogApi

Proyecto del Curso de creación de APIs con Ruby on Rails de Platzi

## Instalación

```shell
sudo bundle install
```

## Scripts

- `rails server`  
Lanza la aplicación

## Versión

Ruby 2.5.1  
Rails 5.2.3

## Instrucciones de configuración inicial

Se instaló _Ruby_

```shell
sudo apt-get install ruby-full
```

Se instaló el _bundler_

```shell
sudo gem install bundler
```

Se instaló _Rails 5.2.3_

```shell
sudo gem install rails -v 5.2.1
```

La creación del proyecto presentó problemas por no encontrar _sqlite3_, se solucionó instalando

```shell
sudo apt-get install sqlite3 libsqlite3-dev
```

```shell
sudo gem install sqlite3-ruby
```

Se crea el proyecto con unas banderas que indican que en lugar de un proyecto completo se precindirá de las vistas y solo se creará la API, también se precindirá de los tests porque crearemos unos propios

```shell
sudo rails new blogapi --api -T
```

El proyecto se creó con grupo y propietario _root_, para cambiarlos al usuario y poder hacer modificaciones sin usar _sudo_

```shell
sudo chown <usuario> blogapi
```

```shell
sudo chgrp <usuario> blogapi
```
