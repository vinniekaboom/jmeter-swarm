# jmeter-swarm

<b>1. Installing Docker on all the cluster of nodes:</b>

                $curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
                $sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
                $sudo apt-get update
                $apt-cache policy docker-ce
                $sudo apt-get install -y docker-ce
                
                $sudo systemctl status docker
                
                $sudo usermod -aG docker ${USER}
                $su - ${USER}
                $id -nG

<b>2. Setting up Swarm Mode Cluster:</b>

<b>On Master Node:</b>

              $docker swarm init --listen-addr <master-ip>:2377 --advertise-addr <master-ip>:2377

<b>On Slave Node:</b>

              $docker swarm join --token <TOKEN> master-ip  <-- Run this command on all the slave nodes

<b>3. Installing Docker Compose on the master node:</b>

            $curl -L https://github.com/docker/compose/releases/download/1.11.2/docker-compose-`uname -s`-`uname -m` > /usr/local 
              /bin/docker-compose
              $chmod +x /usr/local/bin/docker-compose

<b> Pulling the Repository </b>

Login to master node and pull the repository:

                $git clone https://github.com/vinniekaboom/jmeter-swarm.git
                $cd jmeter-dockerized


<b>Running Docker Compose</b>

                sudo docker stack deploy -c docker-compose.yml jm
