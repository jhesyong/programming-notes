# Programming Notes
My notes about programming

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

## NPM
### Fix permission issue
    sudo chown -R $(whoami) ~/.npm

## MacOS
### Refresh LaunchPad
    rm ~/Library/Application\ Support/Dock/*.db ; killall Dock

### Create symbolic link
    ln -s to_be_linked where_to_put_link
