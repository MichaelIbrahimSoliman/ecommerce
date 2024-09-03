this project is under development


the database for  project till now

CREATE TABLE products(
    product_id int NOT NULL PRIMARY KEY,
    name VARCHAR(255), 
    short_description VARCHAR(255), 
    description LONGTEXT, 
    price DOUBLE(53, 11),
    old_price DOUBLE(53, 11), 
    minimumqty INT(255), 
    quantity INT(255), 
    additional_information LONGTEXT,
    shipping_return LONGTEXT,
    slug VARCHAR(255),
    STATUS TINYINT(4),
    is_delete TINYINT(4),
        image VARCHAR(255),
        image_mime VARCHAR(255),
        image_size INT(11),
        deleted_at TIMESTAMP,
        deleted_by BIGINT(20),
        color_id INT(11),
        brand_id INT(11),
        admin_id INT(11),
        categories_id INT(11),
        subcategories_id INT(11),
   
        FOREIGN KEY(color_id) REFERENCES colors(color_id),
        FOREIGN KEY(brand_id) REFERENCES brands(brand_id),
        FOREIGN KEY( admin_id) REFERENCES admins(admin_id),
        
        FOREIGN KEY(categories_id) REFERENCES categories(categories_id),
        FOREIGN KEY(subcategories_id) REFERENCES subcategories(subcategories_id)
)


CREATE TABLE colors(
    color_id INT NOT NULL,
    color_name VARCHAR(255),
    color_description LONGTEXT,
    color_code VARCHAR(255),
    color_status TINYINT,
    is_delete TINYINT(4),
    created_by BIGINT(20),
    deleted_by BIGINT(20),
    created_at TIMESTAMP NULL,
    updated_at TIMESTAMP NULL,
    PRIMARY KEY(color_id)
); CREATE TABLE brands(
    brand_id INT NOT NULL,
    brand_name VARCHAR(255),
    brand_description LONGTEXT,
    brand_slug VARCHAR(255),
    brand_status TINYINT,
    meta_name VARCHAR(255),
    meta_description VARCHAR(255),
    meta_keywords VARCHAR(255),
    is_delete TINYINT(4),
    created_by BIGINT(20),
    deleted_by BIGINT(20),
    created_at TIMESTAMP NULL,
    updated_at TIMESTAMP NULL,
    PRIMARY KEY(brand_id)
); CREATE TABLE admins(
    admin_id INT NOT NULL,
    admin_name VARCHAR(255),
    PRIMARY KEY(admin_id),
    email VARCHAR(255),
    email_verified_at TIMESTAMP NULL,
    PASSWORD VARCHAR(255),
    remember_token VARCHAR(100),
    created_at TIMESTAMP null,
    updated_at TIMESTAMP NULL
); CREATE TABLE categories(
    categories_id INT NOT NULL,
    categories_name VARCHAR(255),
    PRIMARY KEY(categories_id),
    email VARCHAR(255),
    email_verified_at TIMESTAMP NULL,
    PASSWORD VARCHAR(255),
    remember_token VARCHAR(100),
    created_at TIMESTAMP NULL,
    updated_at TIMESTAMP NULL
); CREATE TABLE subcategories(
    subcategories_id INT NOT NULL,
    PRIMARY KEY(subcategories_id),
    subcategories_name VARCHAR(255),
    subcategories_code VARCHAR(255),
    subcategories_description CHAR(255),
    subcategories_slug VARCHAR(255),
    subcategories_keywords VARCHAR(255),
    created_at TIMESTAMP NULL,
    updated_at TIMESTAMP NULL
);

