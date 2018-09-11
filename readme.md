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
