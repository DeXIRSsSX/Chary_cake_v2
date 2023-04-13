CREATE TABLE "Client" (
  id_Client int PRIMARY KEY,
  name varchar(255)  NOT NULL,
  phone int NOT NULL,
  email varchar(255) NOT NULL,
  date date NOT NULL,
  address varchar(255) NOT NULL
);

CREATE TABLE "Employee" (
  id_Employee int PRIMARY KEY,
  name varchar(255)  NOT NULL,
  phone int NOT NULL,
  email varchar(255) NOT NULL,
  date date NOT NULL,
);
create table "Tovar" (
  id_tovar int Primary key,
  name varchar(255) NOT NULL,
  Price money NOT NULL,
  quantity int,  --* колличество
  description varchar(max),  --* описание товара
  category varchar(100) Not null, --* категория
  photo image
);
create table "Zakaz" (
  id_zakaz int primary key,
  tovar int references Tovar(id_tovar),
  quantity int Not null,
  date date NOT NULL,
  klient int REFERENCES Client (id_Client)
);

create table kurier (
  id_kurier int PRIMARY KEY,
  klient int REFERENCES Client (id_Client),
  zakaz int REFERENCES Zakaz (id_zakaz),
  Employee int REFERENCES Employee (id_employee)
);
INSERT INTO Client (name,phone,email,date, address)
VALUES
  ('Nyssa Deleon','813-5436','lobortis.quam.a@outlook.ca','11.09.94','335-4966 Pellentesque Street'),
  ('Deirdre Underwood','539-7815','ac.arcu@outlook.net','06.12.90','P.O. Box 619, 6879 Nibh. Road'),
  ('Holly Russo','725-7706','magna.praesent@aol.couk','08.02.09','Ap #656-7285 Cursus Street'),
  ('Caleb Keith','210-1774','donec.egestas@icloud.net','14.06.01','111-4903 Cras Road'),
  ('Xandra Phillips','811-4674','purus.in@protonmail.couk','03.07.02','P.O. Box 473, 8460 Phasellus Rd.'),
  ('Chloe Frye','658-4492','at.egestas.a@outlook.ca','17.02.03','289-7175 Ornare Rd.'),
  ('Philip Estes','676-3269','laoreet.libero.et@outlook.ca','16.11.98','5317 Molestie Avenue'),
  ('Victor Hopkins','724-7813','magna.et@aol.edu','10.01.03','690-176 Sit Ave'),
  ('Kennan Lester','317-3451','sit.amet@aol.ca','04.04.89','1694 Ipsum St.'),
  ('Anthony Griffin','448-9310','ac.arcu.nunc@protonmail.edu','24.08.99','482-1224 Morbi Road'),
  ('Clark Howard','555-8885','quisque.libero.lacus@icloud.net','20.02.11','Ap #997-7357 Ultrices Rd.'),
  ('Alan Best','632-4921','ridiculus.mus.proin@protonmail.net','21.07.02','Ap #523-1157 Senectus Av.'),
  ('Kirby Woodward','744-4519','integer@icloud.edu','15.03.89','310-5230 Ridiculus St.'),
  ('Ruby Koch','668-1819','a.ultricies@icloud.net','12.12.86','Ap #780-9653 Tempor Ave'),
  ('Vera Payne','168-3533','orci.adipiscing@google.couk','06.08.87','P.O. Box 533, 8963 Et, Road'),
  ('Mannix Olsen','276-0216','ligula.aliquam@icloud.com','25.06.07','Ap #482-9613 Enim, Avenue'),
  ('Shelby Rowland','821-7319','ipsum.non@protonmail.org','25.10.16','Ap #247-797 Magna. St.'),
  ('Warren Gomez','731-7572','molestie.arcu@aol.couk','25.05.13','Ap #729-5910 Erat Rd.'),
  ('Britanney Cruz','309-5652','tempor.erat@aol.couk','22.03.13','666 Tortor Rd.'),
  ('Jocelyn Haney','764-6802','cubilia@icloud.ca','29.07.03','P.O. Box 803, 3717 Nam Avenue');

 INSERT INTO Employee (name,phone,email,date) 
 VALUES
  ('Fletcher Ball','102-8081','velit.eu.sem@aol.net','07.02.13'),
  ('Andrew Gentry','428-3770','scelerisque@icloud.net','12.09.10'),
  ('Dustin Tanner','396-8266','tincidunt.tempus@icloud.com','28.09.00'),
  ('Tashya Haney','133-3457','tellus.phasellus@google.org','24.08.97'),
  ('Maggie Harvey','758-0850','eu.odio@protonmail.net','12.11.90'),
  ('Remedios Harper','641-2574','dui.suspendisse@hotmail.org','22.02.08');
 INSERT into Tovar (name, Price, quantity, description, category, photo)
 VALUES ('Карамельный пирог', 250, 10, 'Карамельный пирог - это нежный десерт с легкой карамельной начинкой и хрустящей корочкой. Идеально подходит для чаепития в кругу семьи или для праздничного угощения гостей.', 'Пироги','pirog.jpg'),
('Торт "Блаженство"', 2500, 10, 'Нежный торт на основе сливочного крема с добавлением фруктов и ягод', 'Торты', 'cake_bliss.jpg'),
('Воздушный торт', 1200, 10, 'Этот торт просто тает во рту, словно воздушный шарик! Состоит из легких бисквитных коржей и нежнейшего воздушного крема на основе сливок и маршмеллоу. Украшен свежими ягодами и цветами.', 'Торты', 'vozdushny_tort.jpg'),
('Шоколадное наслаждение', 1800, 20, 'Этот торт – идеальное сочетание нежного шоколадного бисквита и густого шоколадного крема. Подходит для любителей насыщенного шоколадного вкуса.', 'Торты', 'shokoladnoe_nas.jpg'),
('Фруктовый рай', 2200, 15, 'Освежающий и легкий торт, который подарит вам настоящий фруктовый вкусовой экстаз! Состоит из сочных фруктовых дольчат, свежих ягод и мусса из свежих фруктов.', 'Торты', 'fruktoviy_rai.jpg'),
('Торт "Наполеон"', 300.00, 5, 'Классический торт из тонких слоев сладкого коржа, с нежным кремом на основе сливочного масла.', 'Торты','tort1.jpg'), 
('Пирожное "Эклер"', 20050, 10, 'Классическое французское пирожное в форме трубочки, с кремом на основе заварного крема и шоколадной глазурью.', 'Пирожные','pirog.jpg'),
('Печенье "Овсяное"', 180.00, 20, 'Печенье с добавлением овсяных хлопьев, с нежным ванильным ароматом.', 'Печенье','coockie1.jpg')
