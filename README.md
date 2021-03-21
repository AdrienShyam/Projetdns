## Mode d'emploi

  * avoir sa propre clé publique sous le nom de cle_publique (cp ~/.ssh/cle.pub /cle_publique)
  * puis vagrant up 
  * commande à effectue avant de faire lancer le playbook et les tar seront dans le meme endroits que le playbook:
  * prometheus:
curl -s https://api.github.com/repos/prometheus/prometheus/releases/latest | grep browser_download_url | grep linux-amd64 | cut -d '"' -f 4  | wget -qi -
 * bind_exporter: curl -s https://api.github.com/repos/prometheus-community/bind_exporter/releases/latest | grep browser_download_url | grep linux-amd64 |  cut -d '"' -f 4 | wget -qi -
  * ansible-galaxy collection install community.general
  * ansible-playbook playbook.yml -i inventory
