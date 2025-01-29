
# **TargatedVulnAi**  
🚀 **LLM for Common Vulnerabilities and Exposures (CVEs)**  

## **Overview**  
TargatedVulnAi is a **Large Language Model (LLM) framework** designed to analyze **Common Vulnerabilities and Exposures (CVEs)** in IoT devices such as cameras, routers, switches, and NVRs. It leverages **Natural Language Processing (NLP) and fine-tuning techniques** to transform complex CVE data into actionable insights for cybersecurity experts.  

## **Features**  
✅ **Automated Web Scraping**: Collects real-time CVE data from trusted sources.  
✅ **Generative AI for Summarization**: Converts technical descriptions into concise insights.  
✅ **Exploit Code Generation**: Fine-tuned **CodeT5** to generate proof-of-concept exploits.  
✅ **Q/A & Report Generation**: Uses **Flan-T5 & T5** for structured cybersecurity analysis.  
✅ **Low-Resource Fine-Tuning**: Implements **QLoRA (8-bit quantization + LoRA)** for efficient training.  

---

## **Project Scope**  
📌 **Data Collection & Preprocessing**:  
- Scrapes CVE details from **CVE.org, NVD, and Exploit-DB**.  
- Normalizes text (lowercasing, removing special characters).  
- Tokenized & padded input-output pairs for model training.  
- Dataset split into **90% training, 10% validation**.  

📌 **Model Development & Training**:  
- **Flan-T5 & T5** for text-based CVE summarization and Q/A.  
- **CodeT5** for exploit code generation.  
- **PEFT (LoRA + QLoRA)** for efficient fine-tuning on limited resources.  

📌 **Evaluation & Future Improvements**:  
- Regular updates with **new CVE data** for improved threat intelligence.  
- Expanding dataset to include **real-world attack vectors & exploits**.  
- Enhancing **model security** against **prompt injection attacks**.  
- Cloud deployment for **real-time cybersecurity assessments**.  

---

## **Model Architecture**  
🔹 **CodeT5-Small**: Fine-tuned for **code generation & exploit creation**.  
🔹 **Flan-T5 & T5**: Used for **summarization, Q&A, and automated reporting**.  
🔹 **LoRA + QLoRA**: Parameter-efficient fine-tuning for **low-memory hardware**.  

---

## **Fine-Tuning Process**  
🔹 **Fine-Tuning Flan-T5 with PEFT**  
- Model: `google/flan-t5-small`  
- LoRA Config: `r=8, alpha=32, dropout=0.1`  
- Training: Mixed precision (FP16), gradient accumulation, AdamW optimizer  

🔹 **Fine-Tuning CodeT5-Small with QLoRA**  
- Model: `Salesforce/codet5-small`  
- LoRA Applied to: **Attention layers (`q, k, v, o`)**  
- 8-bit Quantization for **memory efficiency**  

---

## **Training & Optimization**  
⚡ **Dynamic Batching**: Adjusts based on GPU memory.  
⚡ **FP16 Mixed Precision**: Faster computation, lower resource usage.  
⚡ **AdamW Optimizer**: `adamw_bnb_8bit` (optimized for 8-bit training).  
⚡ **Early Stopping**: Prevents overfitting when no improvement is observed.  
⚡ **Logging & Checkpointing**: Saves the best-performing model at each epoch.  

---

## **Future Scope**  
✅ Prevent **Prompt Injection Attacks** for enhanced security.  
✅ Expand dataset with **diverse CVE examples & real-world exploits**.  
✅ Deploy on **cloud infrastructure for real-time vulnerability assessment**.  

---

## **References**  
📌 **CVE Data Source**: [CVE.org](https://www.cve.org/)  
📌 **Exploit Data**: [Exploit-DB](https://www.exploit-db.com/)  
📌 **Model**: [Hugging Face - CodeT5](https://huggingface.co/Salesforce/codet5-small)  

---

**🔒 Securing IoT devices with AI-powered CVE analysis!** 🚀  

---

