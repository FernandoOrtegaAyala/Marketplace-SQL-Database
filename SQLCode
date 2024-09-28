-- Verificación de las DB
SHOW DATABASES;

-- Creación de la DB
CREATE DATABASE marketplace;

-- Utilizacion de la DB actual
USE marketplace;

-- Verificacion de las tablas en la DB
SHOW TABLES;

-- Creación de la tabla usuarios
CREATE TABLE usuarios(
	id_usuario INT UNSIGNED AUTO_INCREMENT NOT NULL PRIMARY KEY,
	nombre_usuario VARCHAR(30) UNIQUE NOT NULL,
	nombre VARCHAR(45)NOT NULL,
	apellidos VARCHAR(45)NOT NULL,
	correo VARCHAR(45) UNIQUE NOT NULL,
	password VARCHAR(45) NOT NULL,
	direccion VARCHAR(100) NOT NULL,
	codigo_postal VARCHAR(15),
	telefono_fijo VARCHAR(25) DEFAULT "Sin numero",
	telefono_celular VARCHAR(25) DEFAULT "Sin numero"
);

-- Insertar datos de prueba en usuarios
INSERT INTO usuarios (nombre_usuario, nombre, apellidos,
	correo, password, direccion, codigo_postal, telefono_fijo, telefono_celular)
	VALUES 
	("Kenai1", "kEnAi","MirCha","kenai@gmail.com", "kenai123", "Direccion4527Estado23", 
	"021260", "123123123", "321321321"),
	("Macario22", "Macario", "Guzman", "macario@outlook.com", "macario2323", "Direccion2380Estado9",
	"235025", "5055548455", "554855055");

-- Insertar datos de prueba en usuarios
INSERT INTO usuarios (nombre_usuario, nombre, apellidos,
	correo, password, codigo_postal, direccion)
	VALUES 
	("Kenai22", "kenai", "MirCha", "kenai22@gmail.com", "kenai123", 
	"021260", "Direccion251Estado1");

-- Verificación de los datos de prueba en usuarios
SELECT *
FROM usuarios

-- Creación de la tabla pedidos
CREATE TABLE pedidos (
	id_pedido INT UNSIGNED AUTO_INCREMENT NOT NULL PRIMARY KEY,
	id_usuario INT UNSIGNED,
	fecha DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
	estado_pedido ENUM ("Pendiente", "Enviado", "Recibido") NOT NULL,
	metodo_pago ENUM ("Tarjeta de credito", "Transferencia Bancaria", "Efectivo", "Paypal"),
	FOREIGN KEY(id_usuario) REFERENCES usuarios(id_usuario)
);

-- Insertar datos de prueba en pedidos
INSERT INTO pedidos (id_usuario, fecha, estado_pedido, metodo_pago)
	VALUES 
	(1, "2023-11-15 13:30:00", "Enviado", "Efectivo");

-- Insertar datos de prueba en pedidos
INSERT INTO pedidos (id_usuario, estado_pedido, metodo_pago)
	VALUES 
	(3, "Pendiente", "Paypal");

-- Verificación de los datos de prueba en pedidos
SELECT *
FROM pedidos;

-- Detalles de las columnas de la tabla pedidos
DESCRIBE pedidos;

-- Creación de la tabla proveedores
CREATE TABLE proveedores (
	id_proveedor INT UNSIGNED AUTO_INCREMENT NOT NULL PRIMARY KEY,
	empresa VARCHAR(30) NOT NULL,
	contacto_nombre VARCHAR(30) NOT NULL,
	correo VARCHAR(30) UNIQUE NOT NULL,
	telefono VARCHAR(30) NOT NULL,
	direccion VARCHAR(100) NOT NULL,
	ciudad VARCHAR(30) NOT NULL,
	pais VARCHAR(30) NOT NULL
);

-- Insertar datos de prueba en proveedores
INSERT INTO proveedores (empresa, contacto_nombre, correo, telefono, direccion, ciudad, pais)
	VALUES
	("bolsos_brand", "bolsos_contacto", "bolsos@correo", "55-55-55", "Direccion55", "Ciudad55", "Pais55"),
	("Carteras_brand", "carteras_contacto", "carteras@correo", "55-56-56", "Direccion56", "Ciudad56", "Pais56"),
	("Relojes_brand", "relojes_contacto", "relojes@correo", "55-57-57", "Direccion57", "Ciudad57", "Pais57"),
	("Ropa_brand", "ropa_contacto", "ropa@correo", "55-58-58", "Direccion58", "Ciudad58", "Pais58"),
	("Zapatos_brand", "zapatos_contacto", "zapatos@correo", "55-59-59", "Direccion59", "Ciudad59", "Pais59"),
	("Perfumeria_brand", "perfumeria_contacto", "perfumeria@correo", "55-60-60", "Direccion60", "Ciudad60", "Pais60"),
	("Joyeria_brand", "joyeria_contacto", "joyeria@correo", "55-61-61", "Direccion61", "Ciudad61", "Pais61"),
	("Accesorios_brand", "accesorios_contacto", "accesorios@correo", "55-62-62", "Direccion62", "Ciudad62", "Pais62"),
	("Cosmeticos_brand", "cosmeticos_contacto", "cosmeticos@correo", "55-63-63", "Direccion63", "Ciudad63", "Pais63"),
	("Hogar_brand", "hogar_contacto", "hogar@correo", "55-64-64", "Direccion64", "Ciudad64", "Pais64"),
	("Electronica_brand", "electronica_contacto", "electronica@correo", "55-65-65", "Direccion55", "Ciudad65", "Pais65"),
	("Arte y Decoracion_brand", "arte_contacto", "arte@correo", "55-66-66", "Direccion66", "Ciudad66", "Pais66"),
	("Delicatessen", "delicatessen_contacto", "delicatessen@correo", "55-67-67", "Direccion67", "Ciudad67", "Pais67"),
	("Automoviles_brand", "automoviles_contacto", "automoviles@correo", "55-68-68", "Direccion68", "Ciudad68", "Pais68"),
	("Instrumentos musicales_brand", "instrumentos_contacto", "instrumentos@correo", "55-69-69", "Direccion69", "Ciudad69", "Pais69"),
	("Viajes_brand", "viajes_contacto", "viajes@correo", "55-70-70", "Direccion70", "Ciudad70", "Pais70");

-- Verificación de los datos de prueba en proveedores
SELECT *
FROM proveedores;

-- Detalles de las columnas de la tabla proveedores
DESCRIBE proveedores;

-- Creación de la tabla productos
CREATE TABLE productos (
	id_producto INT UNSIGNED AUTO_INCREMENT NOT NULL PRIMARY KEY,
	nombre_producto VARCHAR(50) UNIQUE NOT NULL,
	precio DECIMAL(10,2) UNSIGNED NOT NULL, 
	descripcion VARCHAR(255) DEFAULT "Sin descripción",
	categoria ENUM ("Electronica", "Ropa", "Joyeria", "Perfumeria", "Hogar",
	"Cosmeticos", "Accesorios", "Zapatos", "Relojes", "Bolsos", "Carteras",
	"Arte y Decoracion", "Delicatessen", "Automoviles", "Viajes", 
	"Instrumentos musicales") NOT NULL,
	id_proveedor INT UNSIGNED,
	imagenes VARCHAR(255),
	existencias INT UNSIGNED,
	valoraciones DECIMAL(3, 2) DEFAULT 0.00,
	FOREIGN KEY(id_proveedor) REFERENCES proveedores(id_proveedor)
);

-- Insertar datos de prueba en productos
INSERT INTO productos (nombre_producto, precio, categoria, id_proveedor, imagenes,
	existencias)
	VALUES
	("Bolso de mano rosa de lujo para dama", 2500.00, "Bolsos", 1, "https://img.freepik.com/free-photo/color-purple-elegance-woman-luxury_1203-6518.jpg?w=740&t=st=1700103700~exp=1700104300~hmac=8138df78584d4bb6b3aa1e215ceeca69b0940954a76570709f5eb93cc7a493e5",
	12),
	("Bolso de noche con decoración elegante", 3500.00, "Bolsos", 1, "https://images.pexels.com/photos/14706900/pexels-photo-14706900.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1",
	10),
	("Cartera de cuero genuino vintage para caballero", 2000.00, "Carteras", 2, "https://images.pexels.com/photos/4452528/pexels-photo-4452528.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1",
	5),
	("Cartera de piel sintetica en forma de sobre", 1500.00, "Carteras", 2, "https://images.pexels.com/photos/4452400/pexels-photo-4452400.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1",
	3),
	("Reloj de oro estilo retro para caballero", 7800.00, "Relojes", 3, "https://img.freepik.com/free-photo/ensemble-antique-clocks-capturing-essence-time-its-historical-implications_157027-2327.jpg?t=st=1700104846~exp=1700108446~hmac=a1532c41fdfd8d948894eab7e774641c8ec666e6ad4ff269232edf9358e11bda&w=1380",
	2),
	("Reloj mecánico automático", 6500.00, "Relojes", 3, "https://img.freepik.com/premium-psd/abstract-geometric-luxury-podium_401134-179.jpg?w=740",
	1),
	("Vestido Minuet de fiesta largo", 3500.00, "Ropa", 4, "https://img.freepik.com/free-photo/gorgeous-woman-with-blonde-wavy-hair-wearing-elegant-beige-dress_273443-1783.jpg?w=740&t=st=1700105787~exp=1700106387~hmac=eaf043003e857cb55aa1dc11834eacdd4c0b75467a95190e38caea55366dd631",
    4),
    ("Vestido de noche", 3500.00, "Ropa", 4, "https://img.freepik.com/free-photo/woman-with-red-dress-high-heels_329181-10054.jpg?w=740&t=st=1700106733~exp=1700107333~hmac=c2dec59a991412b4fcc2924ddccd3b8e97c51b5535776cf02b7f59e98e4f87f3",
    4),
    ("Traje negro Versanti corte slim", 3800.00, "Ropa", 4, "https://img.freepik.com/free-photo/young-handsome-businessman-black-shirt-black-suit_158595-4781.jpg?w=740&t=st=1700105972~exp=1700106572~hmac=cb802011632fbba55eafec947bc02d44e102fd98a1bc8ad8b611abda0a1aa10d0",
    1),
    ("Zapatos negros de cuero", 2800.00, "Zapatos", 5, "https://img.freepik.com/free-photo/elegant-black-leather-shoes-men-black-background-photo-studio-style-ai-generative_123827-23440.jpg?w=1380&t=st=1700106458~exp=1700107058~hmac=67db80895f13f295c491fd6a007f61f407cad5ee3cd0c00ca93e3176c9cc7697",
    6),
    ("Tacones Altos De Satén Rosa Para Mujer", 3600.00, "Zapatos", 5, "https://img.freepik.com/free-photo/beautiful-asian-bride-portrait-pink_1150-11439.jpg?w=1380&t=st=1700106853~exp=1700107453~hmac=bbbda89aab1173b1e96b4bc00cc453b0036c199a25a209dbc135646174cbaa3a",
    2),
    ("Perfume caballero: Eua de Toilette intenso aroma",
    2300.00, "Perfumeria", 6, "https://img.freepik.com/free-photo/dark-glass-bottle-with-single-liquid-drop-generative-ai_188544-9634.jpg?t=st=1700107048~exp=1700110648~hmac=6b79638a98276e41d5fba34a10e59b0c9d3190e21f1fceb4e08b4d10fb13e214&w=740",
    5),
    ("Perfume Reality dama: Aroma dulce, Eau de Parfum", 2400.00, "Perfumeria", 6, "https://img.freepik.com/free-photo/fresh-scent-purple-flower-glass-bottle-generative-ai_188544-9642.jpg?t=st=1700106934~exp=1700110534~hmac=92287fb0a78567ef184b8ebf63e9ae84ec0bec45d871e8004597b4d9fba384a8&w=826",
    4),
    ("Collar dama 18kt Oro retro accesorio corazón", 6300.00, "Joyeria", 7, "https://img.freepik.com/free-photo/young-woman-wearing-chain-necklace_23-2149490489.jpg?w=740&t=st=1700108113~exp=1700108713~hmac=ce3f38c2cb4c046da118361e23008344962bd1936d9d0521a6f9a57fb5ec4dbe",
    2),
    ("Anillo 18kt con diamantes en pavé", 4000.00, "Joyeria", 7, "https://as1.ftcdn.net/v2/jpg/06/43/38/20/1000_F_643382032_0CraZivr1WBZnXYBXy8J14O3xraCwtop.jpg",
	3),
	("Gafas de sol negras para caballero", 2000.00, "Accesorios", 8, "https://img.freepik.com/free-photo/studio-portrait-charismatic-sensual-macho-with-stylish-hair-sunglasses_613910-11120.jpg?w=1380&t=st=1700108605~exp=1700109205~hmac=5c62a1821fc0924e8bf02e5fa57cbedec4a1ca2c3412e38f414b415d1dd6383e",
	5),
    ("Guantes de invierno tejidos a mano", 1200.00, "Accesorios", 8, "https://img.freepik.com/free-photo/close-up-hand-wearing-watch_23-2148861948.jpg?w=826&t=st=1700108921~exp=1700109521~hmac=2621eb4c5f56efb80a93d3f976e1ddc9bfab2aca57b666b9192703bf5c081941",
    10),
    ("Kit delineador tinta negra: Blackest 0.034 oz", 1000.00, "Cosmeticos", 9, "https://img.freepik.com/free-vector/poster-cosmetic-eyeliner-with-packaging-poster-template_73621-1014.jpg?w=740&t=st=1700109125~exp=1700109725~hmac=40e0f1a794d7aa8c9190dec5f4bc7560ef459fc673c25ad203f94fc71831d055",
    20),
    ("Kit brochas para maquillar mango de acero", 1400.00, "Cosmeticos", 9, "https://img.freepik.com/free-photo/beauty-product-collection-set-with-vibrant-colors-generative-ai_188544-9681.jpg?t=st=1700109385~exp=1700112985~hmac=10e448da529b2b98e43744285cbf1b1f08418ba622ef31f7f52c0bb93d296d4a&w=826",
    12),
    ("Sala modualar de diseñador terracota", 12000.00, "Hogar", 10, "https://img.freepik.com/free-photo/luxury-modern-living-room-with-elegant-design-generated-by-ai_188544-21319.jpg?t=st=1700084644~exp=1700088244~hmac=0b3652ef0a4e29cb8115ad795bf1098c773ac7683df619386960e36961dbc8ee&w=1380",
    3),
    ("Bañera con hidromasaje de 420L marfil", 20000.00, "Hogar", 10, "https://img.freepik.com/free-photo/bathtub-bathroom-with-houseplant-candles-it_181624-49079.jpg?w=826&t=st=1700109992~exp=1700110592~hmac=2896e42ceb1755c7f6102f0776da4105bd7696bfd323819440563ffe64870e57",
    2),
    ("Laptop 8 Núcleos 8GB RAM 512GB SSD", 35000.00, "Electronica", 11, "https://img.freepik.com/free-photo/modern-office-equipment-global-communication-needs-generated-by-ai_24640-87135.jpg?t=st=1700110178~exp=1700113778~hmac=b66f3a97bf001302bf63c044a5391f1b57264e321f9fdf535ac17fc56ab6ae84&w=1380",
    4),
    ("Smartphone color negro 4GB RAM 128GB Memoria", 18000.00, "Electronica", 11, "https://img.freepik.com/free-psd/shiny-smartphone-mock-up_1310-186.jpg?w=1380&t=st=1700110429~exp=1700111029~hmac=8ad42b7ca320fde237995959a2a365436febedecc71851bab98ef260d431ae48",
	10),
	("Lámpara de diseñador buro Litex", 1600.00, "Arte y Decoracion", 12, "https://img.freepik.com/free-photo/elegant-lamp-illuminates-modern-bedroom-with-ornate-generated-by-ai_188544-13299.jpg?w=1380&t=st=1700110773~exp=1700111373~hmac=389cf8237aa6e2422407a2832ed4cf2f448996123bbd72b06bf23caa85f392eb",
	4),
 	("Escultura de ángel mármol 6.5ft decoración", 8000.00, "Arte y Decoracion", 12, "https://img.freepik.com/free-photo/statue-angel-with-wings-wings-sits-table_188544-13322.jpg?t=st=1700167461~exp=1700171061~hmac=808cb259cebd3f3f8d9b95cc54e280a4e65714a402f96b8c15de6662c0f4351e&w=1380",
	1),
	("Vino Vessen: Cosecha premium", 1200.00, "Delicatessen", 13, "https://img.freepik.com/free-photo/elegant-wine-bottle-cup-with-grapes-generative-ai_188544-8088.jpg?t=st=1700168112~exp=1700171712~hmac=c3544ff8fa5b5bc07326c304cb62701c80b11750715f77c8875ef0c3aaa15a58&w=826",
	10),
	("Vino Trésor de vin: Cosecha", 1400.00, "Delicatessen", 13, "https://img.freepik.com/free-photo/freshness-nature-bounty-grape-fruit-wood-table-leaf-generated-by-artificial-intelligence_25030-64756.jpg?t=st=1700169599~exp=1700173199~hmac=fbf91794974b1211ea242c9ebe07aaf37735e699a1521d6e3d61f92d36c95947&w=1380",
	12),
	("Sedan negro: Automático Híbrido hp 51-62L", 4000000.00, "Automoviles", 14, "https://img.freepik.com/premium-photo/black-ford-sedan-parked-cobblestone-street_899870-20049.jpg?w=740",
	3),
	("Guitarra eléctrica tipo Stratocaster", 5600.00, "Instrumentos musicales", 15, "https://img.freepik.com/premium-photo/picture-guitar_931878-348668.jpg?w=826",
	4),
	("Viaje en crucero Oceania hacia Nueva Guinea", 30000.00, "Viajes", 16, "https://img.freepik.com/free-photo/view-luxurious-cruise-ship_23-2150785220.jpg?t=st=1700170713~exp=1700174313~hmac=f9fc15692f4cda8cc6c00fe4cf86a6da10633b74a7f8a2453689692509736c5d&w=740",
	100);

-- Detalles de las columnas de la tabla productos
DESCRIBE productos;

-- Verificación de los datos de prueba en productos
SELECT * 
FROM productos;

-- Creación de la tabla reseñas
CREATE TABLE reseñas (
	id_reseña INT UNSIGNED AUTO_INCREMENT NOT NULL PRIMARY KEY,
	id_producto INT UNSIGNED,
	reseña TEXT,
	calificacion INT CHECK (calificacion IN (1, 2, 3, 4, 5)),
	FOREIGN KEY (id_producto) REFERENCES productos(id_producto)
);

-- Insertar datos de prueba en reseñas
INSERT INTO reseñas (id_producto, reseña, calificacion)
	VALUES
	(1, "Bonito, me encanta el color", 4),
	(2, "Perfecto para salir a cualquier lugar", 4),
	(3, "Elegante diseño minimalista, detalles increibles, de muy buena calidad", 5),
	(5, "Adoro el estilo que transmite, de mis mejores compras", 5),
	(7, "Lo amo, lo he utilizado para momentos especiales, me ha quedado perfecto", 5),
	(9, "El mejor traje, ajuste perfecto, brinda seguridad al usarlo", 5),
	(12, "Se ha vuelto por mucho mi perfume favorito, he recibido muchos cumplidos desde que lo uso", 4),
	(15, "Se lo he regalado a mi prometida y le ha encantado", 4),
	(16, "Ideales para un buen día soleado, cumplen perfecto", 4),
	(18, "Mi favorito al maquillarme, siempre lo uso para un momento especial", 5),
	(21, "Se ha vuelto mi lugar favorito de descanso, es perfecto", 5),
	(22, "Muy buena potencia, corre programas y tareas demandantes muy eficientemente, la recomiendo especialmente para diseño", 4),
	(26, "Adoro su sabor, nunca habia probado algo igual", 4),
	(27, "Ideal para una ocasión especial", 4),
	(28, "Muy buen ahorro de combustible", 4),
	(29, "Mi favorita, tiene un excelente sonido y es muy comoda al tocar", 5);

-- Verificación de los datos de prueba en reseñas
SELECT *
FROM reseñas;

-- Verificación de la relación de las tablas productos y reseñas 
SELECT p.*, r.*
FROM productos AS p
RIGHT JOIN reseñas AS r ON p.id_producto = r.id_producto;

-- Creación de la tabla detalles_pedido
CREATE TABLE detalles_pedido (
	id_detalle INT UNSIGNED AUTO_INCREMENT NOT NULL PRIMARY KEY,
	id_pedido INT UNSIGNED,
	id_producto INT UNSIGNED,
	cantidad INT UNSIGNED NOT NULL,
	FOREIGN KEY (id_pedido) REFERENCES pedidos(id_pedido),
	FOREIGN KEY (id_producto) REFERENCES productos (id_producto)
);

-- Detalles de las columnas de la tabla detalles_pedido
DESCRIBE detalles_pedido;

-- Insertar datos de prueba en detalles_pedido
INSERT INTO detalles_pedido (id_pedido, id_producto, cantidad)
	VALUES
	(1, 1, 2);

-- Insertar datos de prueba en detalles_pedido
INSERT INTO detalles_pedido (id_pedido, id_producto, cantidad)
	VALUES
	(1, 2, 2);

-- Verificación de los datos de prueba en detalles_pedido
SELECT *
FROM detalles_pedido;

-- Consulta de todos los productos asociados a un pedido
SELECT dp.*, p.*
FROM detalles_pedido AS dp
LEFT JOIN productos AS p ON dp.id_producto = p.id_producto;

-- Actualizar existencias del producto debido a una compra
UPDATE productos AS p
JOIN detalles_pedido AS dp ON p.id_producto = dp.id_producto
SET p.existencias = p.existencias - dp.cantidad
WHERE dp.id_pedido = 1;

-- Consulta del valor total de un pedido
SELECT SUM(dp.cantidad * p.precio) AS total_pedido
FROM detalles_pedido dp
JOIN productos p ON dp.id_producto = p.id_producto
WHERE dp.id_pedido = 1;
