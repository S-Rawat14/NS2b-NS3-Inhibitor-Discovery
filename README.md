# NS2B/NS3 protein inhibitor finding
 A ML classification model is created to find potential ligand molecules for NS2B/NS3 proteins to inhibiting Zika virus replication

## **Literature inforamtion**
- The **NS2B and NS3** proteins are essential components of the viral protease complex in **Flaviviruses**, which includes **Zika virus and Dengue virus**. The `NS3 protein acts as the catalytic subunit`, while the `NS2B protein acts as a cofactor`, forming a tightly associated complex that is responsible for the proteolytic processing of the viral polyprotein.
- The NS2B/NS3 protease complex of Zika virus and Dengue virus share a `high degree of structural similarity`, with the overall fold and arrangement of the `two proteins being highly conserved`. The `active site residues` and the `substrate-binding pockets` are also very `similar`, which allows for `the development of pan-Flavivirus inhibitors that can target both Zika and Dengue viruses`.

### **This project is divided into 3 phases:**
 1. Machine Learning classification model building and screening of DrugBank
 2. Virtual screening of potential active molecules using Maestro
 3. Perform MD Simulation of selected molecules using Gromacs

## **1. ML part**
## **Steps involved**
1. NS3 protein bioactivity data collection from CHEMBL
2. Selecting data on the basis of IC50 values
3. Pre-processing data (handling missing values, removing invalid smiles, converting smiles to canonical smiles)
4. Dividing molecules into active and inactive on the basis of IC50 values (**IC50<=5000nM --> Active**, **IC50>=10000nM ----> Inactive**)
5. Generating Morgan fingerprints using rdkit
6. Applying PCA to reduce dimesnion of data
7. Training various machine learning classification models and selecting the best ones
8. Screening drug bank molecules uing trained models to get potential active molecules
- **Result:** 213 potentially active molecules were obtained and were used for virtual screening

## **2. Virtual Screening**
Virtual screening was performed on 213 obtained molecules
- **NS2B/NS3 protein (only A and B chains)**
![image](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/393c5ac4-4f1c-4307-b1c3-11f73042dffe)

- **Docking scores of top molecules**
![image](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/e4c999f7-796b-4a6e-8ef6-b5dcc75fb182)

- **Docked Molecules**
- 1. DB04452
![DB04452](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/b5a34c57-a992-4a90-b4c0-4d2d44ce2d1a)

- 2. DB04591_1
     ![DB04591_1](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/83a609dc-b766-4661-926e-3b430505c505)

 - 3. DB04591_2
      ![DB04591_2](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/ce47601c-a4a1-43d9-a3c9-b4febe1a43d5)

- 4. DB09013
   ![DB09013](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/445b5c33-85aa-460f-8b84-197fc749fbe0)

- 5. DB12831
   ![DB12831](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/a5968c88-3a47-4c87-adb7-243067b315c0)

- 6. DB17692
   
   ![DB17692_1](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/1cd44e05-2d3b-4bb7-be04-dc9d9b518eec)

- 7. DB18036
   
![DB18036_3](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/1ed13dfb-008b-4947-879f-375d783bcb77)
![DB18036_2](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/f498615c-ab72-4cc7-9e6e-6a03d155fa5d)
![DB18036_1](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/2e02f9f9-806f-4f14-8dd4-39abe09bffc7)
![DB18036_4](https://github.com/ankit-singh973/NS2B-NS3-protein-inhibitor-finding/assets/113300592/ec58b355-7e48-4a55-864d-0421ccf0f3f4)

