# Demo omgeving Apigee

## Setup

### Dockerfile setup

In de dockerfile config:

- FROM jenkins/jenkins:lts
- USER root
- RUN apt-get update && apt-get install -y maven
- USER jenkins


### Dockerfile build

Voer het volgende commando uit voor de dockerfile te builden:   
- ***docker build -t jenkins-maven .*** ( . op einde moet mee in command)
  
Voer het volgende commando uit voor container te starten:
- ***docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins-maven***

Deze zal jenkins installeren en builden, tijdens eht build process krijg je een personal admin access key voor als admin in te loggen.

## Configuratie Jenkins

Na het inloggen met de access key kies je vervolgens om verder te gaan als admin, je maakt dus geen user aan. Vervolgens ga je een nieuwe pipeline ontwikkelen.
In general instellen voeg je de link van deze repo toe: https://github.com/DeFranco13/demo-apigee .

<img width="984" alt="Screenshot 2024-03-11 at 15 37 32" src="https://github.com/DeFranco13/demo-apigee/assets/75678058/196c61e0-6d15-4eab-a5ca-4b5d5a5f759f">


Momenteel is deze op public gezet voor het toegankelijk te maken voor de Jenkins api, deze kan worden ingesteld met een password / key in nabije toekomst.
Onder pipeline kies je voor: "Pipeline script from SCM". In de repo link voor je opnieuw de github link to. Momenteel in credentials nog niets toevoegen, dit volgt nog.

![image](https://github.com/DeFranco13/demo-apigee/assets/75678058/52f7dfe5-934e-4f77-aef4-304664d2fe43)




## Gebruik Jenkins

Build now voor de Jenkins te starten.

