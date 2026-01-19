# 🧬 Enhancing the Athlete Biological Passport with Blockchain: A Secure and Transparent Anti-Doping Approach
<p align="center">Enhancing the athlete biological passport with blockchain: A secure and transparent anti-doping approach</p>

<p align="center">
  <a href="https://doi.org/10.1177/17479541251394511">
    <img src="https://img.shields.io/badge/International Journal of Sports Science & Coaching-2025-blue" alt="Feature Requests">
  </a>
</p>

This repository contains the official implementation associated with the paper:  
**“Enhancing the Athlete Biological Passport with Blockchain: A Secure and Transparent Anti-Doping Approach”**  
published in *International Journal of Sports Science & Coaching*, 2025.

> **Authors:**  
> Alejandro Sirvent-Llamas, José Luis Albentosa-Mora, Gaspar Cano-Esquibel, and Higinio Mora  
> **Affiliation:** Department of Computer Technology and Computation, University of Alicante, Spain  
> **Repository:** [https://github.com/cloudlab-aia/ABP-Blockchain](https://github.com/cloudlab-aia/ABP-Blockchain)

---

## 📘 Abstract
The **Athlete Biological Passport (ABP)** is a longitudinal record of an athlete’s biological variables that allows indirect detection of doping practices. Traditional ABP systems face issues of data fragmentation, limited interoperability, and lack of transparency between stakeholders. This project proposes a **blockchain-based ABP framework** implemented on **Hyperledger Fabric**, providing a **secure, immutable, and transparent platform** for managing biological and anti-doping information.  By leveraging **smart contracts**, the system ensures integrity, traceability, and controlled access to sensitive data, fostering trust among anti-doping agencies, laboratories, and sports federations.

---

## ⚙️ Requirements
To reproduce or extend this implementation, ensure the following components are installed:

| Component | Version | Purpose |
|------------|----------|----------|
| Node.js | ≥ 14 | Runtime environment |
| npm | ≥ 6 | Package manager |
| Hyperledger Fabric | v2.2 + | Permissioned blockchain framework |
| Docker / Docker Compose | Latest | Network orchestration |
| Mocha / Chai | — | Testing and validation |

All dependencies are listed in `package.json`.

---

## 🚀 Usage

### 1️⃣ Clone the repository
```bash
git clone https://github.com/cloudlab-aia/ABP-Blockchain.git
cd ABP-Blockchain
```

### 2️⃣ Install dependencies
```bash
npm install
```

### 3️⃣ Run local tests (mock Fabric environment)
```bash
npm test
```

### 4️⃣ (Optional) Deploy on a Hyperledger Fabric network
- Launch a Fabric test network (e.g., from Fabric Samples).  
- Package and install the chaincode:
  ```bash
  peer lifecycle chaincode package abp.tar.gz --path ./ --lang node --label abp_1
  ```
- Approve and commit the definition across peers.  
- Invoke transactions through CLI or SDK clients.

---

## 🧩 Directory Structure
```
ABP-Blockchain/
 ├── athlete.js              # Athlete entity model (docType = "athlete")
 ├── sample.js               # Biological sample model (docType = "sample")
 ├── contract.js             # Smart contract logic (BiologicalPassportContract)
 ├── test-biopassport.js     # Unit tests using Fabric mock stubs
 ├── package.json            # Dependencies and scripts
 └── README.md               # This documentation
 
```

---

## 🧠 Core Smart-Contract Functions

| Function | Description |
|-----------|-------------|
| `initLedger(ctx)` | Initializes the ledger with sample athletes. |
| `registerAthlete(ctx, id, name, sport, nationality)` | Registers a new athlete. |
| `recordSample(ctx, sampleId, athleteId, date, type, result)` | Records a biological sample. |
| `queryAthlete(ctx, athleteId)` | Retrieves athlete data. |
| `querySamplesByAthlete(ctx, athleteId)` | Lists all samples associated with an athlete. |
| `athleteExists(ctx, athleteId)` | Checks if an athlete already exists. |

---

## 📊 Example Data

**Athlete**
```json
{
  "docType": "athlete",
  "athleteId": "ATH123",
  "name": "John Doe",
  "sport": "Cycling",
  "nationality": "USA"
}
```

**Sample**
```json
{
  "docType": "sample",
  "sampleId": "SAMP001",
  "athleteId": "ATH123",
  "date": "2025-01-01",
  "type": "Blood",
  "result": "Negative"
}
```

---

## 📈 Results
This implementation demonstrates the viability of using **permissioned blockchain infrastructures** to enhance the Athlete Biological Passport system by:

- Ensuring **immutability** and **traceability** of all biological data.  
- Enabling **secure multi-party collaboration** among agencies and labs.  
- Supporting **transparent auditability** of anti-doping processes.  
- Preserving **data privacy** through access control and organization-specific channels.  

This prototype serves as a **reference architecture** for applying blockchain to sports integrity and healthcare systems.

---

## 🙌 Acknowledgments
This work has been developed at the **University of Alicante (Spain)** within the **CloudLab-AIA Research Group**, as part of the research line on **Blockchain Applications for Sports Integrity and Anti-Doping Systems**.  
The authors gratefully acknowledge the institutional support and collaboration of all research partners.

---

## 📚 Citation
If you use or reference this repository, please cite:

> **Alejandro Sirvent-Llamas**, **José Luis Albentosa-Mora**, **Gaspar Cano-Esquibel**, and **Higinio Mora**.  
> *Enhancing the Athlete Biological Passport with Blockchain: A Secure and Transparent Anti-Doping Approach.*  
> *International Journal of Sports Science & Coaching*, 2025.  
> GitHub: [https://github.com/cloudlab-aia/ABP-Blockchain](https://github.com/cloudlab-aia/ABP-Blockchain)

```bibtex
@article{sirvent_2025,
	title = {Enhancing the Athlete Biological Passport with Blockchain: A Secure and Transparent Anti-Doping Approach},
	issn = {1747-9541},
	doi = {10.1177/17479541251394511},
	journal = {International Journal of Sports Science & Coaching},
	author = {Sirvent-Llamas, Alejandro and Albentosa-Mora, José Luis and Cano-Esquibel, Gaspar and Mora, Higinio},
	year = {2025},
}
```
---

### 📬 Contact
**Corresponding author:**  
**Alejandro Sirvent-Llamas** — University of Alicante, Spain  
📧 asirvent@ua.es  
🌐 [https://www.ua.es](https://www.ua.es)

## License Information
This project is licensed under the <a href="LICENSE.txt">GPL-3 license</a>.
