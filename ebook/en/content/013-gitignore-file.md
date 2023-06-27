# Gitignore

While working on a Git repository, you will often have files and directories that you do not want to commit, so that they are not available to others using the repository.

In some cases, you might not want to commit some of your files to Git due to security reasons.

For example, if you have a config file that stores all of your database credentials and other sensitive information, you should never add it to Git and push it to GitHub as other people will be able to get hold of that sensitive information.

Another case where you may not want to commit a file or directory, is when those files are automatically generated and do not contain source code, so that you don't clutter your repository. Also, sometimes it makes sense not to commit certain files that contain environment information, so that other people can use your code with their environment files.

To prevent these types of files from being committed, you can create a `gitignore` file which includes a list of all of the files and directories that should be excluded from your Git repository. In this chapter, you will learn how to do that!

### Ignoring a specific file

Let's have a look at the following example if you had a `PHP` project and a file called `config.php`, which stores your database connection string details like username, password, host, etc.

To exclude that file from your git project, you could create a file called `.gitignore` inside your project's directory:

```bash
touch .gitignore
```

Then inside that file, all that you need to add is the name of the file that you want to ignore, so the content of the `.gitignore` file would look like this:

```
config.php
```

That way, the next time you run `git add .` and then run `git commit` and `git push`, the `config.php` file will be ignored and will not be added nor pushed to your Github repository.

That way, you would keep your database credentials safe!

### Ignoring a whole directory

In some cases, you might want to ignore a whole folder. For example, if you have a huge `node_modules` folder, there is no need to add it and commit it to your Git project, as that directory is generated automatically whenever you run `npm install`.

The same would go for the `vendor` folder in Laravel. You should not add the `vendor` folder to your Git project, as all of the content of that folder is generated automatically whenever you run `composer install`.

So to ignore the `vendors` and `node_modules` folders, you could just add them to your `.gitignore` file:

```
# Ignored folders
/vendor/
node_modules/
```
### Ignoring a whole directory except for a specific file

Sometimes, you want to ignore a directory except for one or a couple of other files within that directory. It could be that the directory is required for your application to run but the files created is not supposed to be pushed to the remote repository or maybe you want to have a `README.md` file inside the directory for some purpose. To achieve this, your `.gitignore` file should like like this:

```
data/*
!data/README.md
```

The first line indicates that you want to ignore the `data` directory and all files inside it. However, the second line provides the instruction that the `README.md` is an exception.

Take note that the ordering is important in this case. Otherwise, it will not work.

### Getting a gitignore file for Laravel

To get a `gitignore` file for Laravel, you could get the file from [the official Laravel Github repository] here(https://github.com/laravel/laravel/).

The file would look something like this:

```
/node_modules
/public/hot
/public/storage
/storage/*.key
/vendor
.env
.env.backup
.phpunit.result.cache
Homestead.json
Homestead.yaml
npm-debug.log
yarn-error.log
```

It essentially includes all of the files and folders that are not needed to get the application up and running.

### Using gitignore.io

As the number of frameworks and application grows day by day, it might be hard to keep your `.gitignore` files up to date or it could be intimidating if you had to search for the correct `.gitignore` file for every specific framework that you use.

I recently discovered an open-source project called [gitignore.io](https://www.toptal.com/developers/gitignore/). It is a site and a CLI tool with a huge list of predefined `gitignore` files for different frameworks. 

All that you need to do is visit the site and search for the specific framework that you are using.

For example, let's search for a `.gitignore` file for Node.js:

![Nodejs gitignore file](https://imgur.com/bjT2aHP)

Then just hit the **Create button** and you would instantly get a well documented `.gitignore` file for your Node.js project, which will look like this:

```
# Created by https://www.toptal.com/developers/gitignore/api/node
# Edit at https://www.toptal.com/developers/gitignore?templates=node

### Node ###
# Logs
logs
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
lerna-debug.log*

# Diagnostic reports (https://nodejs.org/api/report.html)
report.[0-9]*.[0-9]*.[0-9]*.[0-9]*.json

# Runtime data
pids
*.pid
*.seed
*.pid.lock

# Directory for instrumented libs generated by jscoverage/JSCover
lib-cov

# Coverage directory used by tools like istanbul
coverage
*.lcov

# nyc test coverage
.nyc_output

# Grunt intermediate storage (https://gruntjs.com/creating-plugins#storing-task-files)
.grunt

# Bower dependency directory (https://bower.io/)
bower_components

# node-waf configuration
.lock-wscript

# Compiled binary addons (https://nodejs.org/api/addons.html)
build/Release

# Dependency directories
node_modules/
jspm_packages/

# TypeScript v1 declaration files
typings/

# TypeScript cache
*.tsbuildinfo

# Optional npm cache directory
.npm

# Optional eslint cache
.eslintcache

# Microbundle cache
.rpt2_cache/
.rts2_cache_cjs/
.rts2_cache_es/
.rts2_cache_umd/

# Optional REPL history
.node_repl_history

# Output of 'npm pack'
*.tgz

# Yarn Integrity file
.yarn-integrity

# dotenv environment variables file
.env
.env.test

# parcel-bundler cache (https://parceljs.org/)
.cache

# Next.js build output
.next

# Nuxt.js build / generate output
.nuxt
dist

# Gatsby files
.cache/
# Comment in the public line in if your project uses Gatsby and not Next.js
# https://nextjs.org/blog/next-9-1#public-directory-support
# public

# vuepress build output
.vuepress/dist

# Serverless directories
.serverless/

# FuseBox cache
.fusebox/

# DynamoDB Local files
.dynamodb/

# TernJS port file
.tern-port

# Stores VSCode versions used for testing VSCode extensions
.vscode-test

# End of https://www.toptal.com/developers/gitignore/api/node
```

### Using gitignore.io CLI

If you are a fan of the command-line, the gitignore.io project offers a CLI version as well.

To get it installed on Linux, just run the following command:

```bash
git config --global alias.ignore \
'!gi() { curl -sL https://www.toptal.com/developers/gitignore/api/$@ ;}; gi'
```

If you are using a different OS, I would recommend checking out the documentation [here](https://docs.gitignore.io/install/command-line) on how to get it installed for your specific Shell or OS.

Once you have the `gi` command installed, you could list all of the available `.gitignore` files from gitignore.io by running the following command:

```bash
gi list
```

For example, if you quickly needed a `.gitignore` file for Laravel, you could just run:

```bash
gi laravel
```

And you would get a response back with a well-documented Laravel `.gitignore` file:

```
# Created by https://www.toptal.com/developers/gitignore/api/laravel
# Edit at https://www.toptal.com/developers/gitignore?templates=laravel

### Laravel ###
/vendor/
node_modules/
npm-debug.log
yarn-error.log

# Laravel 4 specific
bootstrap/compiled.php
app/storage/

# Laravel 5 & Lumen specific
public/storage
public/hot

# Laravel 5 & Lumen specific with changed public path
public_html/storage
public_html/hot

storage/*.key
.env
Homestead.yaml
Homestead.json
/.vagrant
.phpunit.result.cache

# Laravel IDE helper
*.meta.*
_ide_*

# End of https://www.toptal.com/developers/gitignore/api/laravel
```

### Conclusion

Having a `gitignore` file is essential, it is great that you could use a tool like the [gitignore.io](gitignore.io) to generate your `gitignore` file automatically, depending on your project!

If you like the gitignore.io project, make sure to check out and contribute to the project [here](https://github.com/toptal/gitignore.io).
