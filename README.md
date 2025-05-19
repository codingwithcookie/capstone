# WEATHER DRIVER • Practicum Progress (Weeks 2‑6)

## 🚀 Project Overview  
**WEATHER DRIVER** is a mobile app that blends turn‑by‑turn navigation with real‑time severe‑weather intelligence. By overlaying NWS/NOAA storm data onto Google Maps directions, we help travelers steer clear of hazardous conditions.

## 🛠 My Role — Backend Engineer (AWS)  
I own the cloud side: ingesting raw weather feeds, normalizing and storing data, and exposing secure APIs for the React Native app.

---

### ✅ What I Accomplished (Weeks 2‑6)

| Week | Highlights |
|------|------------|
| 2 | • On‑boarded, compared NWS vs. OpenWeather APIs<br>• Created a Docker‑based dev container (LocalStack, Terraform, AWS CLI) |
| 3 | • Built a proof‑of‑concept React app to capture GPS + fetch live weather<br>• Provisioned initial AWS resources via Terraform (VPC, DynamoDB, Secrets Manager) |
| 4 | • Wrote **Lambda #1** to pull zone & point forecasts every 15 min → S3<br>• Added SNS topic to fan‑out backfill jobs |
| 5 | • Chained **Lambda #2** for ETL — normalizes data & upserts to DynamoDB<br>• Implemented IAM least‑privilege roles; integrated with Secrets Manager |
| 6 | • Deployed both Lambdas via AWS SAM CI/CD<br>• Refactored pipeline for ingest → format → alert<br>• Demoed live storm data on mock route for the client |

---

### ⚙️ Challenge & Solution  
**Maintaining a rock‑solid dev environment while Terraform and LocalStack acted unpredictably**—resources looked fine in state files but broke at runtime. I solved it via relentless debug‑and‑iterate cycles:

1. Re‑provisioned stack step‑by‑step, logging every diff until services mirrored real AWS.  
2. Isolated fault‑triggering modules; pinned LocalStack & provider versions.  
3. Wrapped the toolchain in a **Docker dev container that spins up fresh each time VS Code launches**, guaranteeing a clean, repeatable deployment. One script now drops the team into an identical, fully working cloud sandbox—no more “works on my machine.”

---

### 🌱 Key Learnings
* Event‑driven design with chained Lambdas & SNS  
* Faster feedback via local bundling and dev containers  
* Practical IAM: balancing least privilege with developer experience  

---
