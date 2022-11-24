# Technical Test

## I. Theoretical Part (ENG)

### Basics : 
- 1 : A Virtual Private Network (VPN) redirect our internet traffic to a VPN server (it can be yours) before sending it to the intended destination.

- 2 : The Three-way Handsheck occurs during an exchange between two hosts using the TCP protocol. This is a three-step verification that can be defined as host 1 sending a SYN (synchronized) packet to the desired destination. Host 2 will send host 1 a SYN-ACK (synchronize, acknowledge) packet to make it understand that it has received it. Finally host 1 will send an ACK (acknowledge) packet to host 2.

- 3 : An SSL certificate is a numeric certificate which authenticates a site and guarantees user confidentiality by encrypting information between the site and the user.

- 4 : A public/private key system (asymmetric cryptography) is used for encrypt and decrypt messages. Indeed, each person has a public key and a private key. If you send a message with a person’s public key and encrypt it with it, then only the person who has the private key can decrypt it. It's often used for web security.

### Important Questions : 
- 1 : First, in order to protect the expoilation system I would install a complete anti-virus by making a detailed comparison between several of them to choose the best one. In addition, I will configure the fire-wall optimally, so that only the mandatory ports for the desired use are open and the rest (incoming or outgoing) is blocked. 
Then, for virtualization systems I will configure the fire-wall in the same way as for the OS while analyzing the traffic that can enter in order to spot suspicious and malicious packets. 
In terms of protecting the internal and external network, I will only authorise the identified hosts that have permission to connect through the firewall as seen before, but also by configuring the network administration interface optimally, so that only an authorized person can access it. Finally I would also use ethernet and not wifi.

- 2 : To check for vulnerabilities at the application level I will examine the source code to see if there are vulnerabilities or malicious content. Then I will test it in a Virtual Machine to check if it does anything. I would also check if the file is known in a Database of virus, malwares or other.

- 3 : To protect personal workstation I would hold a meeting to present the risks of having a weak password and display it on a post it to remember it, especially for people who are not mature in computer security. After that, I would remove all the post-its with the passwords displayed. I would also ensure that employees do not only have access to the minium required for their work. 

- 4 : In first I’ll see if there are other routes. If there are, then I’ll try each one of them to see if I have access or not. It is possible that a returns directly to the targeted page. Otherwise I can find the logs of an admin and thus access the desired page.
If this does not work then I will try to do a SQL Injection so as to bypass the authentication system if there is a page where you can enter text. If this succeeds, then I must continue to search for the desired page if it is not the right one by looking for other routes for example with dirb or hidden elements.
If this one doesn't work I will try a file upload. If we can upload a file on the site as an image for example I will try to inject a php file that allows to enter CMD commands in the url. This will first allow me to see if there is protection on the type of file that can be uploaded but especially to access the server and therefore to list the folders.
If the file type is limited then I will use the BURP suite that allows HTTP requests. This suite allows you to open a website and listen on it to intercept requests made, but also to send them. When I try to upload a file, I should have a query displayed in the BURP suite.  Once this is done, I will change this by changing the type of the file we sent. For example, if we sent a . php, I will modify its type by an image for example. Finally I will send this request to the site. The file will then be accepted and we can use shell commands in the url.
If i don't find what I want, I do this every time I progress until I find what I’m looking for.

There is a lot more way to bypass sécurity on a website like XSS, blind SQL Injection, deserialization and others.

## II. Pratical Part (FR) : 

Pour la partie pratique, j'ai utilisé le langage python. Sur le site de fakeJSON, il nous est montré comment faire une requête post en python. J'ai donc utilisé celle-ci comme base.
Je n'ai malheureusement pas très bien compris comment s'utilise fakejson et comment voir les requêtes faites sur l'api créée dessus. De même pour le fait d'être identifiable. Faut-il par exemple lancer le script depuis une vm connectée à un vpn, ou alors redirigé les données envoyées sur un autre service d'abord?
Cela a été surtout été un grand défi de recherhe sur l'utilisation des fake api avec python mais je n'ai trouver que peu de ressources dessus excepté celles que j'avais déjà.

Pour utiliser le script, il vous faut d'abord renseigner le token qu'il vous est donné. Vous devez ensuite faire une requete GET sur l'url du site avec le token en paramètre afin de pouvoir récupérer les informations de l'api ciblée.

C'est malheuresement seulement ce que j'ai pu faire en plusieurs heures, beaucoup d'incompréhension comme dit au dessus.