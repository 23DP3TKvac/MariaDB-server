# MariaDB datubāžu nostadināšana

Kods priekš namu parvaldnieks uzdevumām)

## MariaDB servera komandas

#### apt update - lai atjaunot sistēmu
#### apt install mariadb-server - lai intalēt MariaDB 
#### mysql -u 'username' -p; - lai ielagoties MAriaDB iekšā 
#### drop table 'tabulas nosaukums'; - lai nodzest izvelēto tabulu
#### show tables; - lai parādīt izvelētas datubāzes saturu
#### select * from 'tabulas nosaukums'; - lai parādīt izvelētas tabulas saturu
#### desc 'tabulas nosaukums'; - lai parādīt izvelētas tabulas struktūru

## Main kods databāzei

CREATE TABLE ekas (
    id INT PRIMARY KEY auto_increment,
    adrese VARCHAR(255),
    stavi INT,
    m2 INT
);

INSERT INTO ekas (adrese, stavi, m2) VALUES ("Altonavas iela 22A",3,1500);

CREATE TABLE dzivoklis (
    dz_id INT PRIMARY KEY auto_increment,
    numurs INT,
    istabas INT,
    m2 INT,
    stavs INT,
    ekas_id INT,
    FOREIGN KEY(ekas_id) REFERENCES ekas(id)
);

INSERT INTO dzivoklis (numurs, istabas, m2, stavs, ekas_id) VALUES (53, 3, 50, 9, 1);
