#  Exchage rate path problem (frate)


This project aims to solve the problems of:
- Finding the best possible rate for converting a cryptocurrency to fiat currency by identifying the sequence of trades needed across exchanges.
- Able to receive price updates and save/update them in a specified database


## Deploying

In order to deploy the script, some prerequisites are needed:

 1. Python
 2. MySql
 3. Python pip
 4. python-dateutil library

The project is created and tested on linux. The following commands need to be ran on the terminal prior of running the script:

 - sudo apt-get install python-pip
 - sudo apt-get install python-mysqldb
 - pip install python-dateutil

Moreover a database schema needs to be created using the following query:

    CREATE SCHEMA `frateData` ;
the following query will create the table needed:

    CREATE TABLE `edgeWeights` (
	  `id` int(11) NOT NULL AUTO_INCREMENT,
	  `source_exchange` varchar(255) DEFAULT 'null',
	  `source_currency` varchar(45) DEFAULT NULL,
	  `destination_exchange` varchar(255) DEFAULT 'null',
	  `destination_currency` varchar(45) DEFAULT NULL,
	  `edge` varchar(45) NOT NULL DEFAULT '0',
	  `time_entered` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
	  `time_updated` timestamp NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
	  `rate_time_ex` datetime DEFAULT NULL,
	  PRIMARY KEY (`id`)
	) ENGINE=InnoDB AUTO_INCREMENT=109 DEFAULT CHARSET=latin1;

Please clone the project from the master branch

Lastly please navigate into the main file of the project and change the database config located in getMysqlCursor function

## Running the script 
The script is able to both receive prices and save them as well as receive a request for a rate and answer back.
To run the script please navigate into the project's directory and run:

    python main
  on the terminal
  The script is going to prompt you to select between 1 and 2 where 1 is for sending a price update to the project and 2 is to request a rate. 
  Type the desire selection and hit enter.
  Then you can input your request accordingly
A price update input looks like:

    '2017-11-01T09:42:23+00:00 KRAKEN BTC USD 1000.0 0.0009'
   and a rate request looks like: 
   

    'EXCHANGE_RATE_REQUEST KRAKEN BTC GDAX BTC'
  Please ensure to include your request in single quotes as indicated above

The script will then either update the database with the given update price or answer back with the best ate for the given exchange request.
