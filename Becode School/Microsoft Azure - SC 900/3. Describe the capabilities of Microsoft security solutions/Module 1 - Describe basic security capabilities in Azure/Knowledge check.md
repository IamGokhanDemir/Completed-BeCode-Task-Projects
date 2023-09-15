
**Status:** Completed  
**XP:** 200  
**Time:** 2 minutes  

---

**Check your knowledge**

1. The security admin has created an Azure Network Security Group (NSG) to filter network traffic to a virtual machine. The admin wants to allow inbound traffic using the Remote Desktop Protocol (RDP), but the default NSG rules are currently blocking all inbound traffic that is not from another virtual network or an Azure load balancer. What does the security admin have to do to allow inbound traffic using RDP?

   - [ ] Delete the default rule.
   - [x] Create a new network security rule that allows RDP traffic and that has a higher priority than the default rule.
   - [ ] There's nothing the admin can do, RDP traffic isn't supported with NSGs.

2. The security admin wants to protect Azure resources from DDoS attacks and needs logging, alerting, and telemetry capabilities. which Azure service can provide these capabilities?

   - [ ] Default DDoS infrastructure protection.
   - [x] DDoS Network Protection.
   - [ ] Azure Bastion.

3. An organization has several virtual machines in Azure. The security admin wants to deploy Azure Bastion to get secure access to those VMs. What should the admin keep in mind?

   - [x] Azure Bastion is deployed per virtual network, with support for virtual network peering.
   - [ ] Azure Bastion is deployed per subscription.
   - [ ] Azure Bastion is deployed per virtual machine.

4. An organization has much of its application data in Azure. The security admin wants a way to create and control the keys used to encrypt the organization's application data. Which service would the admin use?

   - [ ] Transparent data encryption.
   - [ ] Secrets management.
   - [x] Azure Key Vault.

Please select the best responses for each question and then check your answers.

---

✅ **Answers**:

1. Create a new network security rule that allows RDP traffic and that has a higher priority than the default rule.
2. DDoS Network Protection.
3. Azure Bastion is deployed per virtual network, with support for virtual network peering.
4. Azure Key Vault.