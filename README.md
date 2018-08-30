# newGradsResources
An effective usage of available online resources to the incoming grads in the field of Computer Science

1. Github is an effective tool for every CS student. Github in addition to code repositories it allow you to search for a wide variety of top repositories and their current repositories and many more.
2. Github offers a Student Developer Pack for the students
3. When subscribed for the pack it unleashes a wide variety of online resources.
4. Listing out the top resources 
   a. Github Private Repositories
   b. Digital Ocean Server and hosting ($50 credit)
   c. NameCheap Domain name, SSL certificate (1 year)
   d. many other Amazon AWS, SendGrid (Email).
5. Based on these available resources, we are trying to implement a website domain (NameCheap) hosting on Digital Ocean.
6. Digital Ocean
   a. Signup (provide credit card details initally)
   b. Add the Github coupon to claim the $50 credit
   c. Create a Droplet (Server) - Ubuntu/ Initial package (2GB and 25GB $5/mo)
   d. Get your root login credentials in your registered email
   e. login to the server via Putty (WIndows), change the password.
   f. Follow the instructions "inital setup of ubuntu digital ocean", create a non-root user
   g. install nginx webserver to make sure the server is up and running. (cross check by creating a file under usr/var/html)
   h. Install node, npm, mysql, mongo basic software packages
7. NameCheap Domain registration and SSL
   a. Signup using github (choose a domain name)
   b. you got your domain name
   c. go to settings, under name servers add the digital ocean nameservers
   d. In the diital ocean, for the droplet created add a domain entering the domain created above.
   e. Use the SSL certificate link in the github to redirect to NameCheap and complete the order.
   f. Create csr in the digital ocean following the instructions.
   g. Activate the SSL using the above created csr.
   h. Choose DCV activation method as http
   i. Download the text file and copy it under the var/html folder in your server (ensure it is access via web ip/*.txt)
   j. Once again retry activation in Namecheap and now the SSL certifcate is activated and you will recieve a email with certificate (zip)
   k. copy the zip to the server. Copy both .crt and .ca.bundle into to single .crt file (nginx reads as a single chain file)
   l. Go to /etc/nginx/sites-enabled folder. add the certicate path, key, server name, ssl in the default file.
   m. allow https all through the firewall (nfw) 
   n. if using node server setup a reverse proxy server by adding a location attribute with a route (/) and running server (:3000). Restart       the nginx server after checking syntax. 



