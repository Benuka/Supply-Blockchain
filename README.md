<<<<<<< HEAD
# Supply-Blockchain

### Overview ###

The _Supply Blockchain_ Project is a feasibility study to explore how an industrial supply-chain can be implemented with blockchain technology. Particularly, we use an example from the automobile industry. 

The simulation begins with an automotive production line. The [Contribution guidelines for this project](https://github.com/Lebski/chain_pi) will be migrated to this project in a later development step. 

We also simulate the transportation and the selling of the car. 

This project uses the hyperledger fabric blockchain together with the hyperledger composer tool. 
=======
# Supply-Blockchain Sender

### Overview ###

With the provided source code we handle the sensors for the [Supply-Chain](https://github.com/Lebski/Supply-Blockchain) project. 
We use the MFRC522 Sensor with multiple Raspberry Pi. Each time the Sensor is triggered, we send a JSON object to a MQTT broker. 
A HTTP POST-Request will soon be possible. 

The Project uses some code-snipptes from [MFRC522-python](https://github.com/mxgxw/MFRC522-python)

### Prerequisites ###

python3, git, python-pip3, python-dev, build-essential 

### Installation ###

```bash
sudo pip3 install RPi.GPIO
# also possible: python3 -m pip install RPi.GPIO
printf "device_tree_param=spi=on \ndtoverlay=spi-bcm2708\n" >>  /boot/config.txt
sudo raspi-config 
# Now you have to choose "Advanced Options > SPI"
sudo reboot

git clone https://github.com/lthiery/SPI-Py.git 
cd SPI-Py 
#It is super important to INSTALL WITH PYTHON3
sudo python3 setup.py install 
pip3 install paho-mqtt python-etcd
cd .. 
git clone https://github.com/Lebski/chain_pi
```

### Run ###

```
cd Chain_rfid
nano sender.py
```
Change the receiver (broker here) 
```
receiver = "iot.eclipse.org" 	#Hier die eigene IP Adresse / Domain
port = 1883 			# Hier der eigene Port 
max_timeout = 60 		      # Maximales Timeout 
topic = "supply/sensor1"	# Hier die Topic, auf die der broker hört
```

And then run the Skript: 
```
python3 sender.py
```
>>>>>>> sensors/master
