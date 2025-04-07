# Narration Pronounciation Dictionary

This is the narration dictionary page which is used to teach our AI narrator how to pronounce difficult acronyms and words (mostly libraries and products). For example if the narration pronounces, "IBM" as "ih-buh-mmm" instead of "eye-bee-em" this is the place to fix it!

## How to add a new word to the pronounciation dictionary

1. Update the JSON below (within the `START DICTIONARY` and `END DICTIONARY` comments) with the new update:
  - Key: The word as seen in the instructions in _lowercase_
  - Value: The correct pronounciation spelling (your best guess, use the existing mappings for good examples)
3. Create a new PR of your changes

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
  "z/vm": "zed-vm"
}
// END DICTIONARY
```
