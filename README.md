# UPDATE 

Thanks to Knowledge-Wisdom-Understanding (MrPMillz) for making the script cleaner and fixing the header payloads.

# INSTALLATION

You can install locally or use Docker instead.

If you choose to install locally, follow these steps:

```bash

git clone https://github.com/gotr00t0day/forbiddenpass.git

cd forbiddenpass

pip3 install -r requirements.txt

python3 forbiddenpass.py -h

```

If you prefer using Docker, [click here to jump to the Docker section](#DOCKER).


# USAGE 

```bash

___________         ___.   .__    .___  .___           __________                                        
\_   _____/_________\_ |__ |__| __| _/__| _/____   ____\______   \_____    ______ ______                 
 |    __)/  _ \_  __ \ __ \|  |/ __ |/ __ |/ __ \ /    \|     ___/\__  \  /  ___//  ___/                 
 |     \(  <_> )  | \/ \_\ \  / /_/ / /_/ \  ___/|   |  \    |     / __ \_\___ \ \___ \                  
 \___  / \____/|__|  |___  /__\____ \____ |\___  >___|  /____|    (____  /____  >____  >                 
     \/                  \/        \/    \/    \/     \/               \/     \/     \/   v1.0           
                                                                                                         
                                                                                                         
                                                                                                         
usage: forbiddenpass.py [-h] [-p domain.com] [-d filename.txt] [-t site.com]                             
                                                                                                         
optional arguments:                                                                                      
  -h, --help            show this help message and exit                                                  
  -p domain.com, --path domain.com                                                                       
                        path to check                                                                    
  -d filename.txt, --domains filename.txt                                                                
                        domains to check                                                                 
  -t site.com, --target site.com                                                                         
                        domain to check 
 ```
 
 # EXAMPLE
 
 domains to check
 ```
 python3 forbiddenpass.py -d domains.txt
 ```
 domains to check with a path
 ```
 python3 forbiddenpass.py -d domains.txt --path login
 ```
 scan a single target
 ```
 python3 forbiddenpass.py -t https://site
 ```
 scan a single target with a path
 ```
  python3 forbiddenpass.py -t https://site --path login
 ````

# DOCKER

Follow these steps to install and run ForbiddenPass in Docker.

## Clone the Repository

First, clone the repository:

```bash

git clone https://github.com/gotr00t0day/forbiddenpass.git

cd forbiddenpass
```
## Build the Docker Image

Build the Docker image using the following command in the same directory where the Dockerfile is located.

```bash
docker build -t forbiddenpass .
```
## Usage

Once the image is built, you can run the container using the following commands:

 Domains to check
 ```
 docker run --rm -v $(pwd):/app forbiddenpass -d domains.txt
 ```

 Domains to check with a path
 ```
 docker run --rm -v $(pwd):/app forbiddenpass -d domains.txt --path login
 ```


 > **Note**
-v $(pwd):/app: This option mounts the current working directory on your host machine to the /app directory inside the container. This allows the container to access files in your current directory, such as domains.txt

 > **Note**
Ensure that domains.txt is located in your current working directory when executing the docker run command.
 
Scan a single target
 ```
docker run --rm forbiddenpass -t https://site
 ```
Scan a single target with a path
 ```
  docker run --rm forbiddenpass -t https://site --path login
 ````

# DISCLAIMER

inspired by https://github.com/iamj0ker/bypass-403 </br>
bypass-403 doesn't support scanning multiple domains and I needed to speed things up a bit so forbiddenpass was created
