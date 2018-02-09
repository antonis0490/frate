# frate

sudo apt-get install python-mysqldb



CREATE SCHEMA `frateData` ;

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
) ENGINE=InnoDB AUTO_INCREMENT=7 DEFAULT CHARSET=latin1;


sudo apt-get install python-pip
pip install python-dateutil