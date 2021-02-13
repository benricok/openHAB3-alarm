## openHAB alarm configuration template

### Required openHAB addons
1.  MQTT-broker
2.  myopenHAB-cloud (Optional)

### Installing openhab with the included docker-compose.yml script
1.  Create openhab user
    ```
    sudo useradd -r -s /sbin/nologin openhab 
    ```
2.  Add your user to the openhab group
    ```
    sudo usermod -a -G openhab <your user> 
    ```
3.  Clone this repo and don't cd into it
    ```
    git clone https://github.com/benricok/openHAB3-alarm 
    ```
4.  Copy the template directories to one directory up (outside repo folder)
    ```
    cp -rf "./openHAB3-alarm/config/ (openHAB template)" ./services/openhab/config 
    sudo chown -R openhab:openhab ./services/openhab/config
    cp -rf "./openHAB3-alarm/config/ (mosquitto template)" ./services/mosquitto/config   
    ```
5.  Change the configuration files as you see fit
6.  Change directory to root directory of the repo and run docker-compose.yml script
    ```
    cd openHAB3-alarm && OH_UID=$(id -u openhab) OH_GID=$(id -g openhab) docker-compose up -d
    ```

