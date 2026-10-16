# Parking Lot USB Baiting Incident Analysis & Risk Assessment

## Exercise Overview & Assessment Process

This independent security assessment investigates a physical social engineering incident involving a USB flash drive recovered from an organizational parking lot. The scenario examines how threat actors utilize physical media drops (USB baiting) to compromise target environments, evaluating the risks associated with mixed personal and professional data storage, attacker exploitation vectors, and defense-in-depth mitigation strategies.

---

## Parking Lot USB Exercise Worksheet

### Contents

The USB drive contains a mixture of personal and sensitive work-related files belonging to the human resource manager, Jorge Bailey. Personal files include family and pet photo folders, a wedding list, and a personal resume, while work files include employee shift schedules, new hire letters, and budget trackers. Storing personal and professional data together on removable media violates data segregation best practices and exposes extensive Personally Identifiable Information (PII).

### Attacker Mindset

An attacker could weaponize this information to execute targeted social engineering or spear-phishing campaigns against Jorge, hospital employees, or their relatives. By analyzing personal details such as family names, wedding plans, and schedules, malicious actors can craft convincing pretexts to manipulate targets. Furthermore, if the drive had been plugged into a corporate workstation without virtualization, it could have established a backdoor or delivered malware into the hospital network.

### Risk Analysis

To mitigate USB baiting attacks, organizations must implement layered administrative, technical, and operational controls. Operationally, security awareness training should educate staff never to plug unknown physical media into workstations and to report found devices immediately. Technically, endpoint security policies can disable USB mass storage ports via Group Policy Objects (GPO) or Device Control software, while virtualized analysis environments should be mandated for handling necessary media. Enforcing strict data segregation policies ensures that personal and corporate files are never stored together on portable hardware.

---

## Summary

Physical social engineering remains a potent vector for bypassing perimeter defenses. By combining technical USB port restrictions, mandatory security awareness training, and isolated analysis procedures, organizations can effectively neutralize physical media baiting threats and protect sensitive internal infrastructure.
