# API Usage

## The API is suitable for human, mouse, sheep, monkey. 

## Step1
Create a JSON file with the following content:
```json
{
  "question": "What is the target gene regulated by CRE at chrX:XXX-XXX in the species tissue? The sequence is ATCG..."
}
```

---
## Step2
Press 'Win + R', and type 'cmd'

---

## Step3
Type in cmd with the following content (Replace 'D:/request.json' with the actual file path):
```bash
curl -X POST http://47.75.151.53:8080/analyze -H "Content-Type: application/json" -d @D:/request.json
```
wait for about 3 minutes, and a reply will be given.

---

## If you want to use it for other species, please refer to the following steps:

## Step1
Upload gff/gff3/gtf file
```bash
curl -X POST http://47.75.151.53:8080/upload/genes -F "file=@D:/deer.gtf" -F "taxid=9500" -F "assembly=deer"
```

---
## Step2
Add the taxid and assembly you created to the json file:
```json
{
  "question": "What is the target gene regulated by CRE at chrX:XXX-XXX in the species tissue(taxid=9500, assembly=deer)? The sequence is ATCG..."
}
```

---
## Step3
Upload ATAC, H3K27ac value file(Optional), the file can be in bed/csv/tsv/txt format:
```bash
curl -X POST http://47.75.151.53:8080/upload/elements -F "file=@D:/ATAC.tsv" -F "taxid=9500" -F "assembly=deer"
```

---
### Step4
Upload TAD file(Optional), the file can be in bed/csv/tsv/txt format:
```bash
curl -X POST http://47.75.151.53:8080/upload/tads -F "file=@D:/TAD.txt" -F "taxid=9500" -F "assembly=deer"
```



# Output Fields

| Field | Description |
|------|------------|
| CRE | CRE genomic coordinate |
| TF | Predicted regulatory transcription factor |
| target_gene | Predicted target gene |
| confidence | Confidence score (0–1) |
| importance_score | Biological relevance to tissue development |
| rationale | Explainable multi-step reasoning |
| output | Human-readable summary |

---

# Notes

- All outputs are **regulatory hypotheses**
- Scores are **interpretable, not absolute probabilities**
- Designed to complement experimental validation

---
