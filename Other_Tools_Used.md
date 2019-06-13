# Tools Used
  1. `pigz`: Decompress a Zlib file
  
  ```
  $ pigz -d -z 10_of_clubs.wav
  ```
  2. `find`: Find flags
  
  ```
  find / -iname "*_of_*"
  ```
  3. `mount`: Mount ISO
  
  ```
  $ mount -o loop /home/kylo_ren/.secret_files/my_recordings_do_not_open.iso /media/iso
  ```
  4. `Binwalk`: Analyse binary files for embeded files and executable code
  
  ```
  $ binwalk -e 10_of_clubs.wav
  ```
  5. `docker`: Docker command
  ```
  $ docker ps                                               #View running docker containers
  ```
  ```
  $ docker exec -it 9f48895b1e0e bash                       # Access the docker container
  ```
