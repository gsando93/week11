DROP TABLE IF EXISTS material;
DROP TABLE IF EXISTS step;
DROP TABLE IF EXISTS project_category;
DROP TABLE IF EXISTS category;
DROP TABLE IF EXISTS project;

CREATE TABLE project (
project_id INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
project_name VARCHAR(128) NOT NULL,
estimated_hours INT NOT NULL,
actual_hours INT NOT NULL,
difficulty TEXT NOT NULL,
notes TEXT NOT NULL
);

CREATE TABLE category (
material_id INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
material_name TEXT NOT NULL,
num_required INT,
cost INT,
FOREIGN KEY (project_id) REFERENCES project (project_id) ON DELETE CASCADE
);

CREATE TABLE project_category (
project_id INT NOT NULL,
material_id INT NOT NULL,
PRIMARY KEY (project_id, material_id),
FOREIGN KEY (project_id) REFERENCES project (project_id) ON DELETE CASCADE,
FOREIGN KEY (material_id) REFERENCES material (material_id) ON DELETE CASCADE
);

CREATE TABLE step (
step_id INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
step_text TEXT NOT NULL,
step_order INT NOT NULL,
FOREIGN KEY (project_id) REFERENCES project (project_id) ON DELETE CASCADE
);

CREATE TABLE material (
material_id INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
material_name TEXT NOT NULL,
num_required INT,
cost DECIMAL(7,2),
FOREIGN KEY (project_id) REFERENCES project (project_id) ON DELETE CASCADE
);