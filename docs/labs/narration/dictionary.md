---
title: Dictionary
---

# Narration Pronounciation Dictionary

When the Author Workbench generates audio for your Articles and Instructional Labs they sometimes contains words (e.g. acronyms, libraries, products, etc.) that are mispronounced. This page is used to teach our AI narrator how to pronounce these difficult words correctly.

For example if the narration pronounces, "IBM" as "ih-buh-mmm" instead of "eye-bee-em" this is the place to fix it!

## How to fix the pronounciation of your audio

1. Update the JSON below (within the `START DICTIONARY` and `END DICTIONARY` comments) with the new update:
  - Key: The word as seen in the instructions in _lowercase_
  - Value: The correct pronounciation spelling (your best guess, use the existing mappings for good examples)
2. Create a new PR of your changes
3. Wait for the PR to be approved
4. When the PR is approved the word has been successfully added to the Narration Pronounciation Dictionary.
5. Re-generate the audio for your Article or Instructional Lab

## Important Notes:

- Make sure to keep the keys lowercase

## The Dictionary

```json
// START DICTIONARY
{
  "watsonx.ai": "watsonx-dot-AI",
  "watsonx.data": "watsonx-dot-data",
  "watsonx.governance": "watsonx-dot-governance",
  "cics": "kicks",
  "aspera": "uh-SPAIR-uh",
  "qiskit": "kiss-kit",
  "faiss": "fice",
  "arff": "arf",
  "caikit": "cake-it",
  "catena-x": "kuh-TEE-nuh-X",
  "ceph": "sef",
  "cics": "kicks",
  "cos": "C-O-S",
  "cp4apps": "C-P-4-Apps",
  "dall-e": "doll-E",
  "envizi": "en-VEE-zee",
  "graphiql": "graphee-Q-L",
  "grpcurl": "G-R-P-curl",
  "guac": "gwok",
  "helayers": "H-E-layers",
  "ieee": "I-triple-E",
  "iscsi": "eye-SCUZZY",
  "kserve": "kay-serv",
  "maas360": "mass-three-sixty",
  "microk8s": "micro-kates",
  "mksysb": "make-sys-B",
  "ollama": "oh-LAH-muh",
  "onnx": "ON-ix",
  "postgresql": "post-gress-Q-L",
  "quarkus": "QUARK-us",
  "siem": "sim",
  "tidyr": "TIDY-er",
  "topolvm": "topo-L-V-M",
  "venv": "V-env",
  "virtio": "virt-I-O",
  "vite": "veet",
  "z/os": "zed-O-S",
  "kubecon": "koob-con",
  "knative": "kay-nay-tiv",
  "mnist": "em-nist",
  "shutil": "shoo-till",
  "rhods": "roads",
  "jceks": "J-seeks",
  "unfccc": "U-N-F-triple-C",
  "tririga": "tri-reega",
  "mas": "mass",
  "kubectl": "cube-C-T-L",
  "kubecost": "cube-cost",
  "ripasso": "Wreepasso",
  "siem": "Simm",
  "sql": "ess-queue-ell",
  "sqlite": "ess-queue-ell-lite",
  "mysql": "my-ess-queue-ell",
  "mssql": "em-ess-ess-queue-ell",
  "z/vm": "zed-vm",
  "numpy": "num-pie",
  "scipy": "sigh-pie",
  "pytorch": "pie-torch",
  "keras": "kair-us",
  "scikit-learn": "sigh-kit-learn",
  "matplotlib": "mat-plot-lib",
  "tensorflow": "tensor-flow",
  "huggingface": "hugging-face",
  "jupyter": "ju-pit-er",
  "nginx": "engine-X",
  "kubectl": "kube-c-t-l",
  "kubernetes": "koo-ber-net-ease",
  "yaml": "yam-ull",
  "json": "jay-son",
  "fastapi": "fast-A-P-I",
  "ansible": "an-sib-bull",
  "terraform": "terra-form",
  "airflow": "air-flow",
  "docker": "dock-er",
  "kafka": "kaf-kuh",
  "hadoop": "ha-doop",
  "scala": "skah-luh",
  "elasticsearch": "elastic-search",
  "grafana": "gra-fah-nuh",
  "gitlab": "git-lab",
  "github": "git-hub",
  "jenkins": "jen-kins",
  "axios": "ax-ee-os",
  "redis": "red-iss",
  "nosql": "no-sequel",
  "cors": "C-O-R-S"
}
// END DICTIONARY
```