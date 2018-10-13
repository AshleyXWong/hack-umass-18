### Configuration ###

##### Clone and Setup Repository
```sh
Clone and enter repo:
$ git clone https://github.com/psheppard16/hack-umass-18
$ cd hack-umass-18
```

##### Configuring and starting vagrant
```sh
Download VirtualBox.

Download Vagrant.

Create environment:
    command line:
        $ vagrant up
    pycharm:
        tools -> vagrant -> up
        tools -> vagrant -> reload
    
    Start ssh session:
    command line:
        $ vagrant ssh
    pycharm:
        tools -> Start SSH session... -> Vagrant at ...
    
Navigating to the project:
$ cd /vagrant
```

##### Base Dependencies
```sh
Update apt-get:
$ sudo apt-get update

Install pip:
$ sudo apt-get install python3-pip

Create and activate virtual environment:
$ sudo pip3 install virtualenv
$ virtualenv --always-copy .venv
$ source .venv/bin/activate

Install pip requirements:
$ pip3 install -r requirements.txt

Install node:
$ curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
$ sudo apt-get install -y nodejs
$ sudo apt-get install npm

Install gulp globally:
$ sudo npm install -g gulp

Set node to development mode
$ sudo npm config set -g production false

Install node requirements:
On mac/linux:
    $ npm install
On windows:
    $ npm install --no-bin-links
    You may need to run:
    $ nodejs node_modules/node-sass/scripts/install.js
    $ npm rebuild node-sass --no-bin-links

Create settings_secret.py using template:
$ cp dog/settings_secret.py.template dog/settings_secret.py

Enter random characters for the 'SECRET_KEY' in `settings_secret.py`:
SECRET_KEY='super random characters'

Collect static resources for main site:
$ sudo gulp (`sudo gulp watch` for continuous collection)

Collect static resources for admin site:
$ sudo python3 manage.py collectstatic
```

##### Project Dependencies
```sh
$ sudo apt-get install freecad
```

##### Database Setup
```sh
Install sqlite3:
$ sudo apt-get install sqlite3

Make the database:
$ cd databases
$ sqlite3 db.sqlite3
sqlite> .exit
$ cd ..

Make migrations: 
$ python manage.py makemigrations

Run migrations: 
$ python manage.py migrate

Create a super user:
$ python manage.py createsuperuser

Populate database with default models:
$ python manage.py configure_dog

```


##### Running the django web server
##### Run the server
```sh
Run the django site:
$ source .venv/bin/activate
$ python3 manage.py runserver 0.0.0.0:8000
Go to 127.0.0.1:8000 to access the site
```

### Documentation

##### Contributing
```sh
Documentation is written with [Sphinx](http://www.sphinx-doc.org/en/stable/). 
The .rst files are located in the `sphinx` folder.

To open the documentation in your browser:
$ python manage.py open-docs

To build the documentation after changes:
$ python manage.py build-docs
```

### Testing ###

##### Running tests locally
```sh
Run all tests:
$ driver=chrome REMOTE_USER=admin python manage.py --keepdb

Run specific tests: 
$ driver=[driver] REMOTE_USER=admin python manage.py --keepdb testing.[test file].[test class].[test]
```

### Anaconda Install ###

$ wget -c https://repo.continuum.io/archive/Anaconda3-5.0.1-Linux-x86_64.sh
$ bash Anaconda3-5.0.1-Linux-x86_64.sh

$ export PATH=/home/vagrant/anaconda3/bin:$PATH
$ conda update --prefix /home/vagrant/anaconda3 anaconda

Create Anaconda Environment
$ conda create -n retinanet python=3.6 anaconda

Activate Environment and install packages
$ source activate retinanet
$ conda install tensorflow numpy scipy opencv pillow matplotlib h5py keras

$ pip install --upgrade pip

Install ImageAI Library
$ pip install https://github.com/OlafenwaMoses/ImageAI/releases/download/2.0.1/imageai-2.0.1-py3-none-any.whl

download this:
https://github.com/OlafenwaMoses/ImageAI/releases/download/1.0/resnet50_coco_best_v2.0.1.h5
copy this file^ to your working folder

also download this:
https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/06/I1_2009_09_08_drive_0012_001351-768x223.png
this is just a test image, and name it image.png

