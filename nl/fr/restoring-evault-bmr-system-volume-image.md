---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restauration d'une image de volume système BMR depuis EVault 

Si vous avez besoin  de restaurer une sauvegarde d'image Bare Metal depuis EVault, vous pouvez la restaurer rapidement depuis notre système EVault BMR Rescue Kernel. Celui-ci vous permet de restaurer le système sans besoin d'un système d'exploitation amorçable. Cette option est très utile si le système d'exploitation n'est plus utilisable ou que les unités du système ont été remplacées.

## Initialisation du système EVault BMR Rescue Kernel

Vous pouvez accéder au système EVault BMR Rescue Kernel via le portail {{site.data.keyword.slportal}}.
1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Cliquez sur **Stockage** > **Sauvegarde**. 
3. Cliquez sur la **flèche** en regard du coffre.
4. Cliquez sur **Lancer Bare Metal Restore**. Cette action déclenche une transaction dont l'exécution prend quelques minutes. Vous pouvez ensuite accéder au serveur en suivant la procédure décrite ici. Un e-mail vous sera envoyé à l'issue du processus d'amorçage du système.


## Restauration depuis le noyau EVault BMR Rescue Kernel

1. Une fois la transaction EVault BMR Rescue Kernel chargée, vous pouvez y accéder de deux manières différentes. 
  - Via un client VNC et l'adresse IP publique/privée de votre serveur, avec le mot de passe répertorié dans le portail {{site.data.keyword.slportal}} 
  - Via la console KVM de votre carte IPMI. Les deux méthodes fonctionnent bien. 
2. Lorsque vous vous connectez pour la première fois à EVault BMR Rescue Kernel, vous êtes accueilli par un écran de sélection de langue. Sélectionnez celle de votre choix, puis cliquez sur **Suivant**.
<br/>![Figure 1 : sélection de langue BMR](/images/bmr1.png)<br/> Vous accédez alors au contrat de licence du logiciel. 
3. Si vous acceptez ses dispositions, cochez la case et cliquez sur **Suivant** pour continuer. <br/> Vous accédez alors au menu de restauration système principal d'EVault. 
4. Pour cette opération, sélectionnez **Restaurer mon système**.
<br/>![Figure 2 : menu BMR principal](/images/bmr2.png)
5. L'assistant de restauration système d'EVault s'affiche. Il fournit une présentation générale de ce qui doit être fait et des étapes nécessaires. Sélectionnez **Suivant** pour continuer. 
<br/>![Figure 3 : assistant BMR](/images/bmr3.png)
6. Sélectionnez le type de sauvegarde depuis lequel effectuer la restauration. Sélectionnez **Logiciel EVault**, puis cliquez sur **Suivant** pour continuer.
7. Dans l'écran **Emplacement de la sauvegarde**, sélectionnez le coffre et entrez son adresse, le numéro du compte EVault, ainsi que le nom d'utilisateur et le mot de passe du compte EVault. Cliquez ensuite sur **Suivant** pour continuer.
<br/>![Figure 4 : sélection de l'emplacement de la sauvegarde](/images/bmr4.png)
8. Votre système devrait à présent être listé sur cet écran. Vérifiez qu'il est sélectionné et cliquez sur **Suivant**.
<br/>![Figure 5 : sélection de votre système](/images/bmr5.png)
9. Sur l'écran **Sélection du travail de sauvegarde**, sélectionnez le travail à utiliser pour la restauration et cliquez sur **Suivant**.
<br/>![Figure 6 : sélection de votre point de restauration](/images/bmr6.png)
10. Dans le menu **Sélection du point de restauration**, sélectionnez celui de votre choix et cliquez sur **Suivant**.
<br/>![Figure 8 : sélection d'un point de restauration](/images/bmr8.png)
11. Sélectionnez les volumes source et de destination. Pour restaurer la source sur la destination,, faites glisser le volume source sur le volume de destination.
<br/>![Figure 9 : sélection de volumes source et de destination](/images/bmr9.png)
12. Dans la fenêtre de confirmation du format ou de fusion des données, deux options sont présentées. Pour les besoins de cet article, sélectionnez **Format** pour une restauration avec nettoyage, laquelle formate le disque. Si vous désirez fusionner les données sur le volume de destination, sélectionnez **Fusionner**.
<br/>![Figure 10 : sélection d'une fusion](/images/bmr10.png)
13. Sur l'écran principal du volume source et de destination, cliquez sur **Suivant**.
14. Sur l'écran récapitulatif du plan de restauration, cochez la case pour accepter le plan et cliquez sur **Suivant**.
<br/>![Figure 11 : lancement de la restauration](/images/bmr11.png)
15. L'écran de progression de la restauration s'affiche et indique la progression de l'opération.
<br/>![Figure 12 : progression de la restauration](/images/bmr12.png)
16. A son terme, une fenêtre de notification vous avise que la restauration a abouti. Cliquez sur **OK**.
17. Sur l'écran de progression de la restauration, cliquez sur **Suivant**.
18. Sur l'écran final, cochez la case de redémarrage du système et sélectionnez **Terminer**. Le serveur est amorcé avec votre image de volume restaurée. La restauration est à présent terminée. <br/>
  **Remarque **: la première fois que ceci se produit, un message d'arrêt inattendu s'affiche. Ceci est tout à fait normal avec ce type de sauvegarde et disparaîtra après le premier amorçage. 