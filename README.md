# BlogApi

Proyecto del Curso de creación de APIs con Ruby on Rails de Platzi

## Instalación

```shell
sudo bundle install
```

## Scripts

- `rails server`  
Lanza la aplicación
- `bundle exec rspec`  
Lanza los tests
- `RAILS_ENV=test rails c`  
Ejecuta la consola en el ambiente de pruebas
- `rails routes`  
Verificación de rutas
- `rails routes | grep "posts"`  
Verificación de rutas de posts

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

## Instalación de gemas necesarias

- **RSpec:** Para los tests
- **shoulda-matchers:** Validaciones para RSpec
- **factory-bot:** Creación de modelos falsos para los tests
- **database-cleaner:** Limpiar la base de datos después de cada ejecución de un test
- **faker:** Permite generar información falsa muy útil para los tests

Después de agregar las gemas en el archivo `Gemfile` las instalamos con el comando

```shell
sudo bundle install
```

Luego generamos los archivos de configuración de _RSpec_

```shell
rails generate rspec:install
```

## Instrucciones de desarrollo

### Creación de modelos

Modelo de usuario

```shell
rails g model user email:string name:string auth_token:string
```

Modelo de post

```shell
rails g model post title:string content:string published:boolean user:references
```

Para destruir modelos usamos el comando

```shell
rails destroy model <model>
```

Luego corremos las migraciones

```shell
rails db:migrate
```

## Generación de factories con factory-bot

Factory de usuario

```shell
rails g factory_bot:model user email:string name:string auth_token:string
```

Factory de post

```shell
rails g factory_bot:model post title:string content:string published:boolean user:references
```

Esto nos genera los archivos en el directorio `test/factories` que podemos arreglar con _Faker_
