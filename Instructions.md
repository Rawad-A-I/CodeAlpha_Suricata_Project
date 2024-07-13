## Instructions
After installing suricata: 

### Custom Rules:
1. **Download the custom.rules file**
2. **Add the custome.rules file to rule path, mainly in /var/lib/suricata/rules (But it could be different)** :
   Open folder where you downloaded the custom.rules:
   
   ```bash
   sudo mv custom.rules /var/lib/suricata/rules

3. **Configure Suricata with the custom rules**:
 
   ```bash
   sudo nano /etc/suricata/suricata.yaml
Here search for rule path ( if using nano use ctrl W and type "rule-path" ).

Add the name of the file like this:

   ![Screenshot_20240713_105656](https://github.com/user-attachments/assets/eef38430-7696-4bef-b834-47f89131f278)

4. **Test Suricata Configuration**:

   ```bash
   sudo suricata -T -c /etc/suricata/suricata.yaml -i eth0
-Note: You can choose the wireless interface you want, I am sticking with eth0

-If all works well you should get this message:

![Screenshot_20240713_110432](https://github.com/user-attachments/assets/f11dd732-69b0-4c74-bf7c-fb83503f1504)

5. **Running Suricata**:
    ```bash
   sudo suricata -c /etc/suricata.yaml -i eth0

6. **Testing For Nmap**:
   while suricata is running you can use any of these Nmap commands:
   ```bash
   nmap -sS 192.168.1.10   # SYN Scan
   nmap -sF 192.168.1.10   # FIN Scan
   nmap -sX 192.168.1.10   # Xmas Scan
   nmap -sN 192.168.1.10   # Null Scan
   nmap -sV 192.168.1.10   # Version Detection
Note: change ip address to yours.

7.**Checking log files**:

After using Nmap and closing suricata you can check log files here:
   ```bash
   sudo tail -f /var/log/suricata/fast.log
```
You should get something Like this:

![Screenshot_20240713_112208](https://github.com/user-attachments/assets/ffdd238b-ac82-49f3-b367-31c89054c4e2)

8.**Additional Logs**:

```bash
sudo tail -f /var/log/suricata/eve.json
sudo tail -f /var/log/suricata/http.log
sudo tail -f /var/log/suricata/dns.log
```







