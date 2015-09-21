# Programming Notes

## PHP
### Set error log file
    ini_set("log_errors" , "1");
    ini_set("error_log" , "errors.log.txt");
    ini_set("display_errors" , "0");

## Ionic
### Solve same-origin policy while development
In `ionic.project`, add

    "proxies": [
      {
        "path": "/api",
        "proxyUrl": "http://some.where/api"
      }
    ]
    
In code, do like this

    var server = 'http://some.where/api';
    
    // if origin exists, use proxy
    if (location && location.origin.indexOf('http') === 0) {
      server = location.origin + '/api';
    }

## MySQL
### Create user and grant privileges
    CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
    GRANT ALL PRIVILEGES ON dbname.* To 'user'@'localhost' IDENTIFIED BY 'password';

### Kill background process
    killall -9 mysqld

### Character set & Collate
    ALTER DATABASE dbname DEFAULT CHARACTER SET='utf8';
    ALTER DATABASE dbname DEFAULT Collate='utf8_unicode_ci';

## Git
### Archive all files
    git archive HEAD --format=zip > archive.zip

### Zip different files between commits
    git diff --name-only commit_old commit_new | zip filename.zip -@

## Deployment
### Set folder permission
Make both the user and apache (www-data) able to access the folder (including files created afterward).

    sudo chown -R $(whoami):www-data folder_name
    sudo chmod -R g+s folder_name

## NPM
### Fix permission issue
    sudo chown -R $(whoami) ~/.npm

## MacOS
### Refresh LaunchPad
    rm ~/Library/Application\ Support/Dock/*.db ; killall Dock

### Create symbolic link
    ln -s to_be_linked where_to_put_link
