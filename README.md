# Final Exam — DevOps Infrastructure Level 1 (SQA113-G1)

**Student:** Giovanna Pietra Nicolodi
**Course:** SQA113-G1 — DevOps Infrastructure Level 1
**Institution:** CCTB

---

## Question Answers

### Q1: What does Immutable Infrastructure mean?

Immutable infrastructure is a deployment model where servers and components are **never modified after they are created and deployed**. Instead of patching or updating a running server, you:

1. Build a new server image (e.g. a Docker image or an AMI) that includes the desired changes.
2. Deploy the new image alongside or in place of the old one.
3. Destroy the old server once traffic has shifted.

**Key benefits:**
- **Consistency** — every instance in an environment is identical; no configuration drift.
- **Reliability** — since nothing is modified in-place, there are no partial updates or failed patches leaving a server in an unknown state.
- **Easy rollbacks** — just redeploy the previous image.
- **Auditability** — all changes are version-controlled through the image build process.

Tools commonly used: Docker, Terraform, Packer, AWS AMIs.

---

### Q2: Explain the command `$ docker exec -it Ubuntu /bin/bash`

| Part | Meaning |
|------|---------|
| `docker exec` | Run a command inside an **already-running** container (unlike `docker run` which starts a new one) |
| `-i` | Keep **stdin open** — interactive mode, so you can type input |
| `-t` | Allocate a **pseudo-TTY** (terminal), giving you a proper shell prompt |
| `Ubuntu` | The **name** (or ID) of the target running container |
| `/bin/bash` | The command to execute — opens a **Bash shell** inside the container |

**In plain English:** "Open an interactive bash terminal inside the running container called Ubuntu."

This is one of the most common debugging commands in Docker — it lets you inspect files, run commands, and troubleshoot a live container from the inside, just like SSH-ing into a server.

---

## Firebase Projects

| Environment | Project ID |
|-------------|------------|
| Testing     | final-gpn |
| Staging     | final-gpn-stg |
| Production  | gpn-default |

---
