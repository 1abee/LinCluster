Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"
  (1..4).each do |i|
    config.vm.define "node-#{i}" do |node|
      node.vm.hostname = "node-#{i}"
      # Размер диска
      node.vm.disk :disk, size: "15GB", primary: true      

      # Приватная сеть для MPI-коммуникаций
      node.vm.network "private_network", ip: "192.168.50.1#{i}"
      
      # Ресурсы 
      node.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
        vb.cpus = 1
      end
    end
  end
end
