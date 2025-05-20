# Let's Play with Azure

![Azure Basic Resource Definitions](/azure-rds.svg)

|     |                                |            |              |                                 |
| ----| ------------------------------ | ---------- | ------------ | ------------------------------- |
| One | `Network/virtualNetwork`       | contains   | zero or more | `Network/networkInterface(s)`.  |
| One | `Network/networkInterface`     | is within  | one          | `Network/virtualNetwork`.       |
| One | `Network/networkInterface`     | uses       | zero or more | `Network/publicIpAddresse(s)`.  |
| One | `Network/publicIpAddresse`     | is used by | zero or one  | `Network/networkInterface`.     |
| One | `Network/networkInterface`     | uses       | zero or one  | `Network/networkSecurityGroup`. |
| One | `Network/networkSecurityGroup` | is used by | zero or more | `Network/networkInterface(s)`.  |
| One | `Compute/virtualMachine`       | has        | one  or more | `Network/networkInterface(s)`.  |
| One | `Network/networkInterface`     | has        | zero or one  | `Compute/virtualMachine`.       |
| One | `Compute/sshPublicKey`         | is used by | zero or more | `Compute/virtualMachine(s)`.    |
| One | `Compute/virtualMachine`       | uses       | zero or more | `Compute/sshPublicKey(s)`.      |
