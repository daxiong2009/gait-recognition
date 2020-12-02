# Gait Recognition Using Neural Network 
<p>This project is presented at the poster session of 2019 Physics-Informed Machine Learning workshop in Seattle, WA.</p><br>
<p> Gait analysis is one of the popular topics that are used in clinical research and biomechanical research. Earliest history of gait analysis dates back to Aristole, who observed people walking with bare eye. Nowadays, with the aid of modern motion capaturing system and wireless sensors, researcher is able to obtain massive amount of data in a single data collection session. Therefore, the problem of how to collect more data from subject become how to extract meaningful information from the data.</p><br>
<p> Machine learning is one of the fastest growing fields in data science, and has been used extensively in business setting. The goal of this project is to classify the walking status (shod walking vs. barefoot walking) using neural network algorithms. <p><br>

## Raw Data Visualization 
<p>The raw dataset contains 396 stride cycles of shod walking and 374 stride cycle of barefoot walking, which was collected from 20 female subjects. The raw data is confidential, but you can get some idea from the following plot 
<img src="image/plot_combo.jpg">

<p><em>from the plot, we found that the kinematics between shod walking and barefoot walking has very similar shape of graph. Although some differences can be spotted in the average plot in the third column, remeber this is the average plot and there are individual difference and variability between subject. Therefore, what set two walking status apart is not the magnitude of the plot, but the time evolution</em></p>

## Data Preprocessing
<p><b>Training-Testing Data Split:</b> I randomly select 350 stride cycles from each walking satus, altogether 700 stride cycle is combined for model training. This training dataset is a 100*700 matrix. The rest will be utilitzed for model testing.</p> 

'''
index1=randperm(396,350);
index2=randperm(374,350);

index1_c=~ismember(1:396,index1); 
index2_c=~ismember(1:374,index2);

a=[x2(:,index1)  x5(:,index2)];    
b_knee=[x2(:,index1_c) x5(:,index2_c)]; 
'''

