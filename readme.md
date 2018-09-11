TODO:
  inventory_hostname: ten host dang thuc thi.
  - Day la bien ansible support san
  - Can phai tim hieu cac bien default ansible variables

- name: demo
  fail:
    msg: "run on {{ inventory_hostname }}"
  when: inventory_hostname =='host2'
Kiem tra neu hostname la host2 thi thuc thi
neu hostname khong phai la host2 thi skip

serial: 1
  - thực thi tất cả các tásk trên từng host rồi mới qua host mới.
  - Can su dung khi muon upgrade tuan tu tung webserver ma khong phai off tat ca cac web server.

delegate_to:  {{ group['lb'][0] }}
  - Chỉ thực thi trên group lb ở index 0.

handlers:
  - Thuc thi callback khi changed = true

ansible-playbook -i hosts web-app.yml -vvvv
ansible-playbook -i hosts nginx.yml -vv

ansible localhost -m command -a  "uname -r"

=================================================
=================================================
shutdown --help
shutdown [OPTIONS...] [TIME] [WALL...]

Shut down the system.

     --help      Show this help
  -H --halt      Halt the machine
  -P --poweroff  Power-off the machine
  -r --reboot    Reboot the machine
  -h             Equivalent to --poweroff, overridden by --halt
  -k             Don't halt/power-off/reboot, just send warnings
     --no-wall   Don't send wall message before halt/power-off/reboot
  -c             Cancel a pending shutdown

unit: min
example:
shutdown -h 30    ( tat sau 30 phut )
shutdown -r now  ( restart ngay lap tuc )
shutdown -c         ( cancel shutdown )

