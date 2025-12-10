# GRAAL: GRAph ALigner

A topological network alignment algorithm that uncovers biological function and phylogeny.

## Authors

- Oleksii Kuchaiev*
- Tijana Milenkovic*
- Vesna Memisevic
- Wayne Hayes
- Natasa Przulj

*\* These authors contributed equally to this work*

**Corresponding Author:** Prof. Natasa Przulj  
📧 natasa.przulj@mbzuai.ac.ae

## Overview

GRAAL (GRAph ALigner) is a pioneering topological network alignment algorithm designed to align biological networks based on their structure. The method reveals biological function and phylogenetic relationships through network topology analysis.

**Paper:** "Topological network alignment uncovers biological function and phylogeny"

## Resources

### Supplementary Materials

- **[Supplementary Information](http://www0.cs.ucl.ac.uk/staff/natasa/GRAAL/GRAAL_SI.pdf)**
- **[Supplementary Table 1](http://www0.cs.ucl.ac.uk/staff/natasa/GRAAL/TableS1.doc)**
- **[Supplementary Table 2](http://www0.cs.ucl.ac.uk/staff/natasa/GRAAL/TableS2.doc)**
- **[Supplementary Table 3](http://www0.cs.ucl.ac.uk/staff/natasa/GRAAL/TableS3.doc)**
- **[Supplementary Table 4](http://www0.cs.ucl.ac.uk/staff/natasa/GRAAL/TableS4.doc)**
- **[Supplementary Table 5](http://www0.cs.ucl.ac.uk/staff/natasa/GRAAL/TableS5.doc)**
- **[Supplementary Table 6](http://www0.cs.ucl.ac.uk/staff/natasa/GRAAL/TableS6.doc)**
- **[Supplementary Table 7](http://www0.cs.ucl.ac.uk/staff/natasa/GRAAL/TableS7.doc)**
- **[Supplementary Table 8](http://www0.cs.ucl.ac.uk/staff/natasa/GRAAL/TableS8.doc)**
- **[All Supplementary Materials (ZIP)](http://www0.cs.ucl.ac.uk/staff/natasa/GRAAL/ALL_SI.zip)**

*Note: If download links don't work when clicked, copy and paste the URLs directly into your browser's address bar.*

## System Requirements

- **Operating System**: Linux (tested on Gentoo and Mandriva distributions, should work on others)
- **Python**: Required for running GRAAL
- **Network Format**: LEDA `.gw` format

## Installation

```bash
git clone https://github.com/przulj-lab/GRAAL.git
cd GRAAL
chmod +x GRAALRunner.py
```

## Requirements

- Networks in LEDA `.gw` format
- Python installed on your system

### Important Constraint

⚠️ **The number of nodes in the first network must not be greater than the number of nodes in the second network!**

## Usage

### Display Help

```bash
./GRAALRunner.py
```

This will display usage directions and available parameters.

### Basic Command

```bash
./GRAALRunner.py alpha network1.gw network2.gw output_prefix
```

### Sample Usage

Navigate to the GRAAL directory and run:

```bash
./GRAALRunner.py 0.8 testGraph1.gw testGraph2.gw result
```

### Parameters

- `alpha` - Weight parameter (e.g., 0.8) for balancing topological similarity
- `network1.gw` - First network file (LEDA format)
- `network2.gw` - Second network file (LEDA format)
- `output_prefix` - Prefix for output alignment files

## Input File Formats

### Network Format

GRAAL accepts networks in LEDA `.gw` format.

## Converting Edge Lists to LEDA Format

If your network is in edge list format:
```
node1 node2
node3 node4
...
```

Use the provided `list2leda` script (included in `CodeAndTestData.zip`):

```bash
./list2leda edgelist.txt >> graph.gw
```

**Note:** Self-loops, directionality, and double edges will be ignored during conversion.

## Example Workflow

1. **Prepare your networks in edge list format**
2. **Convert to LEDA format**:
   ```bash
   ./list2leda network1_edgelist.txt >> network1.gw
   ./list2leda network2_edgelist.txt >> network2.gw
   ```
3. **Run alignment with alpha=0.8**:
   ```bash
   ./GRAALRunner.py 0.8 network1.gw network2.gw alignment_result
   ```

## Output

GRAAL produces alignment files with the specified output prefix, containing node-to-node mappings between the input networks based on topological similarity.

## GRAAL Family of Aligners

- **[C-GRAAL](https://github.com/przulj-lab/C-GRAAL/)** - Common-neighbors-based alignment
- **[L-GRAAL](https://github.com/przulj-lab/L-GRAAL/)** - Lagrangian-based alignment
- **[MI-GRAAL](https://github.com/przulj-lab/MI-GRAAL/)** - Matching-based integrative alignment

## Troubleshooting

### Python Not Found
Ensure Python is installed and in your PATH:
```bash
python --version
```

### Permission Denied
Make the runner script executable:
```bash
chmod +x GRAALRunner.py
```

### Network Size Mismatch
Ensure the first network is smaller than or equal to the second network in size.

## Contact

For questions or issues, please contact Prof. Natasa Przulj at natasa.przulj@mbzuai.ac.ae
