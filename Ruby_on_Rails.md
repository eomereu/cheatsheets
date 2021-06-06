# Ruby on Rails with MongoDB
## Installation
```bash
$ sudo apt update
$ sudo apt-get install ubuntu-dev-tools
$ sudo apt install ruby
```

<details>
<summary><b>Deprecated</b></summary>

## Installation *(Continuing)*
```bash
$ sudo apt install ruby-railties
$ sudo gem install rails
$ sudo apt install ruby-bundler
$ sudo apt install ruby-dev
```

## Create Project (MongoDB)
```bash
rails new myproject --api --skip-active-record
```
```r
development:
  clients:
    default:
      uri: 'mongodb://127.0.0.1:27017/task-manager-api'
      options:
        server_selection_timeout: 1
  options:
test:
  clients:
    default:
      database: tracer_test
      hosts:
        - localhost:27017
      options:
        read:
          mode: :primary
        max_pool_size: 1
```

## Install Gem Dependencies
Within the root of the project:
```bash
$ bundle install
```

</details>

## Create Project
[Guide Video](https://www.youtube.com/watch?v=_U8lgQ-oGpg&ab_channel=WEBteamUniversity)  
[Mongoid Documentation](https://docs.mongodb.com/mongoid/current/tutorials/getting-started-rails/)

> *Mongoid allows us to communicate with our mongo database. 'Mongoose - Node' ~ 'Mongoid - Ruby'*

Create project
```bash
$ rails new myproject --skip-active-record
```
Head to the project root
```bash
$ cd myproject
```
Modify *Gemfile* to add *mongoid*
```r
# add 'mongoid'
gem 'mongoid', '~> 7.0.5'
```
Install gem dependencies
```bash
$ bundle
```
Create a config file *(will be created at **config/mongoid.yml**)*
```bash
$ rails g mongoid:config
```
- If a warning as *"Warning: the running version of Bundler (2.1.2) is older than the version that created the lockfile (2.1.4). We suggest you to upgrade to the version that created the lockfile by running `gem install bundler:2.1.4`."* appears, simply run
  ```bash
  $ gem install bundler:2.1.4
  ```
- If configuration hangs
  ```bash
  $ spring stop
  $ spring start
  ```
  Then run `rails g mongoid:config` again

Modify `raise_not_found_error` to `true` by firstly uncommenting in *mongoid.yml*
```r
    # Raise an error when performing a #find and the document is not found.
    # (default: true)
    raise_not_found_error: false
```
Create a ***scaffold*** 
> *Basically it is a model, however it will also create *view* and *controller* for us!*
```bash
$ rails g scaffold Trace latitude:float longitude:float
```
To add *created_at* and *updated_at* features, include within **model**
```r
  include Mongoid::Timestamps
```
To set our root route, go to **routes.db** under **config** and add
```r
  root 'traces#index'
```
To simply add a new trace go to **/traces/new** and add one  
After adding a sample to simply view it head to the terminal:
```bash
$ mongo
> use traces_development
> db.traces.find().pretty()
{
  "_id" : ObjectId("60bc..."),
  ...
}
```