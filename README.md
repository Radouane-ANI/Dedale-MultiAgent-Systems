# 🗺️ Dedale — Exploration Coopérative & Chasse Multi-Agents (JADE)

[![Java](https://img.shields.io/badge/Java-11%2B-orange.svg?logo=openjdk)](https://openjdk.org/)
[![JADE](https://img.shields.io/badge/Framework-JADE-blue.svg)](https://jade.tilab.com/)
[![GraphStream](https://img.shields.io/badge/Graph-GraphStream-green.svg)](http://graphstream-project.org/)

Projet d'ingénierie des **Systèmes Multi-Agents (SMA)** réalisé dans le cadre du Master FoSyMa (*Fondements des Systèmes Multi-Agents*) à **Sorbonne Université**.

Ce projet conçoit et implémente des architectures d'agents intelligents autonomes et coopératifs capables de naviguer, cartographier et résoudre des objectifs distribués dans un environnement inconnu et partiellement observable.

---

## 🎯 Objectifs de la Mission

Dans un graphe topologique non orienté généré dynamiquement et patrouillé par des créatures hostiles (Golems) :
1. **Exploration distribuée asynchrone** : Explorer intégralement la topologie du graphe en fusionnant les connaissances sans coordination centralisée.
2. **Collecte et transport de ressources** : Coordination entre agents collecteurs (`DummyCollectorAgent`) et camions-citernes (`DummyTankerAgent`) pour optimiser la capacité d'emport.
3. **Protocole de traque et d'encerclement de Golems** : Stratégie collaborative d'interception et de siège d'entités mobiles adverses.

---

## 🤖 Architecture des Comportements (JADE Behaviours)

Les agents reposent sur une machine à états finis (**FSM**) et des comportements communicants asynchrones :

- **`ExploCoopBehaviour`** : Algorithme de recherche en profondeur / largeur distribuée priorisant les nœuds ouverts non visités.
- **`ShareMapBehaviour` & `ShareMapFSMBehaviour`** : Échange direct de sous-graphes topologiques et synchronisation des connaissances cartographiques entre agents lors des croisements.
- **`HuntBehaviour` & `ReceiveSiegeStatusBehaviour`** : Protocoles de communication de position des Golems et établissement dynamique d'un siège coopératif pour bloquer les issues.
- **`OpportunisticBehaviour`** : Adaptation dynamique de mission en fonction de l'énergie et des trésors découverts.
- **`MapRepresentation`** : Modélisation interne du monde basée sur GraphStream pour le calcul des plus courts chemins (Dijkstra) et la détection d'impasses.

---

## 🚀 Lancement du Projet

### Prérequis
- Java JDK 11 ou supérieur
- Maven ou IDE (Eclipse / IntelliJ)

### Exécution
Lancer la classe principale avec la configuration choisie :
```bash
# Compilation et lancement via Maven
mvn clean compile exec:java -Dexec.mainClass="eu.su.mas.dedaleEtu.princ.Principal"
```

Les paramètres de simulation (taille du graphe, nombre d'agents, présence de golems) sont configurables dans [`ConfigurationFile.java`](dedale-etu/src/main/java/eu/su/mas/dedaleEtu/princ/ConfigurationFile.java).

---

## 👥 Auteurs
- **Radouane Aouini**
- **Riadh Ouazib**

*Rapport d'ingénierie complet disponible dans le fichier [`9-Ouazib-Aouini.pdf`](9-Ouazib-Aouini.pdf).*
