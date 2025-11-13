  # ICT171 Cloud Server Project  
### Exotic Car Rental Website – AWS EC2 Deployment  
**Student Name:Kevin Paul
**Student Number:35096522

## Site - http://luxuryrentals.click/

Project Overview
The project involves deploying a fully functional Exotic Car Rental Website on an AWS EC2 Ubuntu server. The website showcases luxury cars and allows users to view car specifications and proceed to a simulated booking page.
The goal is to demonstrate:
Understanding of cloud infrastructure
Server deployment and management
Web hosting using Apache
HTML/CSS website development
Working with Linux-based environments

---

##  Live Server Link  
Your website is hosted on an Ubuntu EC2 instance and can be accessed here:

 **http://51.20.9.27/index.html**

---

## Project Overview  
This project implements a fully functional **Exotic Car Rental Website** hosted on an **Ubuntu Server running on AWS EC2**.  
The server was configured manually using the Linux terminal, Apache web server, and SCP uploads.

This project demonstrates:
- Cloud hosting (IaaS)
- Linux server configuration
- Apache web server setup
- Website deployment (HTML/CSS)
- File transfer using scp
- GitHub documentation and version control

---

##  Website Structure  
/var/www/html
│
├── index.html            (Homepage)
├── style.css             (Styling for all pages)
│
├── ferrari.html          (Ferrari specs page)
├── lamborghini.html      (Lamborghini specs page)
├── mclaren.html          (McLaren specs page)
│
├── booking.html          (Booking page – date, time, payment)
│
├── ferrari.jpg
├── lamborghini.jpg
└── mclaren720s.jpg

Setting Up the AWS EC2 Instance (Step-by-Step)
Go to AWS console → EC2 → Launch Instance

Choose Ubuntu (Free Tier)
Select t2.micro
Create a new key pair (.pem)
Configure security group → allow HTTP (80) and SSH (22)
Launch instance


Connect to EC2 Using SSH
   - ssh -i "your-key.pem" ubuntu@51.20.9.27

## Update Server & Install Apache
  - sudo apt update && sudo apt upgrade -y
    sudo apt install apache2 -y
    sudo systemctl start apache2
    sudo systemctl enable apache2


## Website Development Steps
  - To create a homepage: sudo nano index.html
  - Create car pages: sudo nano ferrari.html
                      sudo nano lamborghini.html
                      sudo nano mclaren.html
  - Create a booking page: sudo nano booking.html

## Adding Images to the Website
  - scp -i "key.pem" ferrari.jpg ubuntu@51.20.9.27:/var/www/html/
    scp -i "key.pem" lamborghini.jpg ubuntu@51.20.9.27:/var/www/html/
    scp -i "key.pem" mclaren720s.jpg ubuntu@51.20.9.27:/var/www/html/
(Note: Above I have just mentioned "key.pem", use the name of the .pem folder which contains the key.

## Referencing Images in HTML
  - <img src="ferrari.jpg" alt="Ferrari">
    <img src="lamborghini.jpg" alt="Lamborghini">
    <img src="mclaren720s.jpg" alt="McLaren">


Note- All induvidual codes for each car pages iduvidually is attached in the word document via screenshots.

## Booking Page Description
The booking.html page allows the user to:
- Select date
- Select time
- Choose a payment method
- Click “Confirm Booking”
    

## Connecting Domain to EC2 Server
Buy your domain (e.g., luxuryrentals.click) from Namecheap.
Use FreeDNS (or Namecheap DNS) to manage your domain.
Add DNS records pointing to your EC2 IP:
  - Type: A
    Host: @
    Value: 51.20.9.27       # your EC2 public IP
    TTL: Automatic

Save changes and wait for DNS propagation


    




