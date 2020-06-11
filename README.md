# Devise Skeleton
This is a basic skeleton of a rails 6.0.3.1 app with Devise, Bootstrap, PosgreSQL, and Foreman. In this setup guide I assume familarity with Ruby on Rails as well as comfort with the terminal and git.

## Initial Setup
### 0. Foreman
Make sure you have installed [**Foreman**](https://github.com/ddollar/foreman).
**DO NOT** add to your Gemfile!

```
gem install foreman
```
Make sure you have installed and setup **PostgreSQL**.
[Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-use-postgresql-with-your-ruby-on-rails-application-on-ubuntu-18-04)
[Mac](https://www.digitalocean.com/community/tutorials/how-to-use-postgresql-with-your-ruby-on-rails-application-on-macos)

### 1. Clone repo
The below command will clone Devise Skeleton with a clean .git file.
```
# /dir_for_projects/

git clone --depth=1 git@github.com:CargoElf/Devise-Skeleton.git && rm -rf Devise-Skeleton/.git && cd Devise-Skeleton && git init
```
### 2. Rename app in project
Included in Devise Skeleton is the [**Rename**](https://github.com/morshedalam/rename) Gem. Before you use it run **Yarn**.
```
# /dir_for_projects/Devise-Skeleton/

yarn
```
Pretty easy.
```
bundle && rails g rename:into new_app_name && cd ../new_app_name
```
Not only will this update the name in your app, it will update update the name of the directory containing the app.

You'll most likely want to remove Rename from your Gemfile after the new name is in place. Make sure your in your new app directory before running these commands.

For Linux
```
# /dir_for_projects/new_app_name/

sed -i "/gem 'rename'/d" Gemfile && bundle
```
For Mac
```
# /dir_for_projects/new_app_name/

sed -i '' "/gem 'rename'/d" Gemfile
bundle
```
Commit those changes if you haven't already.
###3. Update remote URL to your repo
Setup a new repo using your host of choice.

Now point the URL at your new repo.
```
# /dir_for_projects/new_app_name/

git remote set-url git@hostname:USERNAME/REPOSITORY.git
```
### 4. Do some Rails setup
Set the default port you want the app to run on. To do so edit the .env file in the root of the application directory.
```
# /dir_for_projects/new_app_name/.env

PORT=some_port_number
```

Create your DB, migrate and such.
### 5. Get to coding!
To spin up your app use Foreman.
```
foreman start
```
If you want to run it on a different port temporarily, use -p.
```
foreman start -p 3040
```
Go nuts with your new app!
