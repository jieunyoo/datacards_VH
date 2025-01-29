# datacards_VH

combineCards.py SR1pass2016APV=SR1pass2016APV.txt SR1fail2016APV=SR1fail2016APV.txt  TopCRpass2016APV=TopCRpass2016APV.txt SR1pass2016=SR1pass2016.txt SR1fail2016=SR1fail2016.txt  TopCRpass2016=TopCRpass2016.txt SR1pass2017=SR1pass2017.txt SR1fail2017=SR1fail2017.txt  TopCRpass2017=TopCRpass2017.txt SR1pass2018=SR1pass2018.txt SR1fail2018=SR1fail2018.txt  TopCRpass2018=TopCRpass2018.txt > model_combined.txt

 text2workspace.py model_combined.txt -o workspace.root

combine -M MultiDimFit -n _initialFit_Test --algo singles --redefineSignalPOIs r --rMin -20 --rMax 20 --robustFit 1 -m 200 -d workspace.root --setParameters r=1 -t -1 --cminDefaultMinimizerStrategy 1

 combineTool.py -M Impacts -d workspace.root -m 200 --rMin -20 --rMax 20 --robustFit 1 --doFits -t -1 --cminDefaultMinimizerStrategy 1
