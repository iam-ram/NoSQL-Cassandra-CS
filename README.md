# NoSQL-Cassandra-CS
Steps to install Cassandra in Ubuntu

1. Install Java Oracle Virtual Machine

  sudo add-apt-repository ppa:webupd8team/java
  
  sudo apt-get update
  
  sudo apt-get install oracle-java8-set-default
  
2. Install Cassandra

  echo "deb http://www.apache.org/dist/cassandra/debian 22x main" | sudo tee -a /etc/apt/sources.list.d/cassandra.sources.list
  
  echo "deb-src http://www.apache.org/dist/cassandra/debian 22x main" | sudo tee -a  /etc/apt/sources.list.d/cassandra.sources.list
  
  NOTE - Use 23x for latest version of Cassandra

3. Add Public keys from Apache Foundation associated with the package repositories

  gpg --keyserver pgp.mit.edu --recv-keys F758CE318D77295D
  
  gpg --export --armor F758CE318D77295D | sudo apt-key add -
  
  gpg --keyserver pgp.mit.edu --recv-keys 2B5C1B00
  
  gpg --export --armor 2B5C1B00 | sudo apt-key add -
  
  gpg --keyserver pgp.mit.edu --recv-keys 0353B12C
  
  gpg --export --armor 0353B12C | sudo apt-key add -
  
4. Start Cassandra

  sudo apt-get update
  
  sudo apt-get install cassandra

5. Check id Cassandra is installed and running

  sudo service cassandra start
  
  NOTE - If Cassandra is not running, check init script and apply following fix

  sudo nano +60 /etc/init.d/cassandra
  
    /etc/init.d/cassandra
    
    CMD_PATT="cassandra.+CassandraDaemon" must be CMD_PATT="cassandra"
    
    sudo reboot


