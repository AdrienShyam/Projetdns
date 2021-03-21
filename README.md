## Mode d'emploi

  * avoir sa propre clé publique sous le nom de cle_publique (cp ~/.ssh/cle.pub /cle_publique)
  * puis vagrant up 
  * ansible -m ping -i inventory all
  * ansible-galaxy collection install community.general
  * ansible-playbook playbook.yml -i inventory
