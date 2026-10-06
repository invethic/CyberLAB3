# CyberLAB3
introduction to vulnerable industrial protocols like Telnet, using wireshark they have to parse the login attempt and deduce the successful password, 

TP — Analyse d'un protocole industriel vulnérable (Telnet) avec Wireshark
Module Cybersécurité — Ingénieurs par l'alternance GI‑CNAM Thème : écoute réseau (sniffing) et faiblesse des protocoles OT/ICS non chiffrés.
Les apprenti·e·s analysent une capture réseau réelle (anonymisée) dans laquelle un poste d'ingénierie se connecte à un équipement industriel exposant Telnet (port 23) et SSH (port 22). L'objectif est de reconstituer la session Telnet, d'en extraire l'identifiant et le mot de passe réellement validé, puis de comprendre — par comparaison avec le flux SSH chiffré du même équipement — pourquoi les protocoles en clair n'ont plus leur place sur un réseau industriel.

Objectifs pédagogiques
À l'issue du TP, l'apprenti·e est capable de :
    1. Charger et explorer une capture dans Wireshark (hiérarchie des protocoles, conversations).
    2. Identifier un flux applicatif à partir de ses ports et le repérer dans la couche transport (TCP).
    3. Reconstituer une session en clair avec Follow TCP Stream.
    4. Distinguer une tentative d'authentification échouée d'une tentative réussie et en déduire le secret valide.
    5. Construire des filtres d'affichage pertinents.
    6. Expliquer, exemples à l'appui, la nécessité du chiffrement et proposer des contre‑mesures adaptées au contexte OT/ICS.
Pré‑requis
    • Wireshark 4.4.x (ou équivalent récent).
    • Notions de base sur la pile TCP/IP et le modèle OSI.
    • (Optionnel) CyberChef pour la partie « aller plus loin ».
Contenu du dépôt
tp-telnet-wireshark-ot/
├── README.md                     ← ce fichier
├── enonce/
│   └── TP_Telnet_Wireshark.md    ← énoncé étudiant (questions + annexe filtres)
├── corrige/
│   └── CORRIGE_formateur.md      ← corrigé formateur (NE PAS publier aux étudiants)
├── captures/
│   └── capture_telnet_industriel.pcap   ← capture anonymisée (Telnet + SSH)
└── images/                       ← captures d'écran éventuelles
Déroulé conseillé (≈ 2 h)
Temps
Séquence
15 min
Mise en situation OT + prise en main de la capture
30 min
Identification du flux Telnet, handshake TCP, Follow TCP Stream
20 min
Extraction des identifiants + analyse échec/réussite
20 min
Comparaison Telnet vs SSH (même équipement)
20 min
Construction de filtres + statistiques
15 min
Contre‑mesures OT et synthèse
⚠️ Cadre légal et éthique
L'interception de communications sur un réseau que l'on ne possède pas ou pour lequel on n'a pas d'autorisation explicite est illégale (art. 323‑1 et s. du Code pénal). La capture fournie est fictive et anonymisée, destinée à un usage strictement pédagogique en environnement de laboratoire isolé.
À propos de la capture
La capture a été anonymisée à partir d'un échange de démonstration : adresses IP ré‑écrites sur un plan de laboratoire (10.10.10.0/24), adresses MAC fictives (localement administrées, préfixe 02:…), identifiants remplacés et horodatage réinitialisé. Le détail des transformations figure dans le corrigé.

Matériel pédagogique — réutilisable dans le cadre du module. Pensez à conserver le dossier corrige/ hors de portée des étudiants (dépôt privé ou branche protégée).
