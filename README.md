# MariaDB datubāžu nostadināšana

Kods priekš namu parvaldnieks uzdevumām)
## MariaDB servera komandas

1.apt update - lai atjaunot sistēmu
2.apt install mariadb-server - lai intalēt MariaDB 
3.mysql -u <lietotajs> -p - lai ielagoties MAriaDB iekšā 
4.drop table; - lai nodzest izvelēto tabulu
5.show tables; - lai parādīt databazes saturu
6.select * from <tabulas nosaukums> - lai parādīt izvelētas tabulas saturu
7.desc <tabulas nosaukums> - lai parādīt izvelētas tabulas struktūru

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
