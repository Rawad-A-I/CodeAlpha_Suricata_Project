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

5. ** Running Suricata**
