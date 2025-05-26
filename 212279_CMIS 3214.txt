use WayaRest;

create TABLE admin(
adm_id INT AUTO_INCREMENT PRIMARY KEY,
username VARCHAR(50) UNIQUE,
password VARCHAR(255),
email VARCHAR(100) NOT NULL UNIQUE,
code VARCHAR(50),
date TIMESTAMP default CURRENT_TIMESTAMP
);

create table res_category_table(
cid INT AUTO_INCREMENT PRIMARY KEY,
cname VARCHAR(100) NOT NULL UNIQUE
);

create table Users(
uid INT AUTO_INCREMENT PRIMARY KEY,
username VARCHAR(100) NOT NULL UNIQUE,
F_name VARCHAR(50) NOT NULL,
L_name VARCHAR(50) NOT NULL,
email VARCHAR(100) NOT NULL UNIQUE,
password VARCHAR(255),
phone VARCHAR(50) NOT NULL,
Address TEXT NOT NULL,
status INT DEFAULT 1,
date TIMESTAMP default CURRENT_TIMESTAMP
);

create table users_orders(
oid INT AUTO_INCREMENT PRIMARY KEY,
uid INT,
title VARCHAR(150) NOT NULL,
quantity INT NOT NULL,
price DECIMAL(4) NOT NULL,
status VARCHAR(10) DEFAULT NULL,
date TIMESTAMP default CURRENT_TIMESTAMP,
constraint FK_UID FOREIGN key (uid) REFERENCES Users(uid)
);




create table resturant_table(
rs_id INT AUTO_INCREMENT PRIMARY KEY,
c_id INT,
title VARCHAR(150) NOT NULL,
email VARCHAR(100) UNIQUE,
phone VARCHAR(50) NOT NULL,
url VARCHAR(100) NOT NULL,
o_hr VARCHAR(50),
c_hr VARCHAR(50),
o_days VARCHAR(50), 
address TEXT NOT NULL,
image TEXT,
CONSTRAINT FK_CID FOREIGN KEY (cid) REFERENCES res_category_table(cid)
 );


create table dishes_table(
d_id INT AUTO_INCREMENT PRIMARY KEY,
rs_id INT,
CONSTRAINT FK_rsid FOREIGN KEY (rs_id) REFERENCES resturant_table(rs_id)
);
