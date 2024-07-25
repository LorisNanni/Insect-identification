# Insect-identification
Insect identification by combining different neural networks

the code of the IGTD/DeepINS/Wave is available at https://github.com/LorisNanni/Vector-to-matrix-representation-for-CNN-networks-for-classifying-astronomical-data

the code of SVM is available at https://www.csie.ntu.edu.tw/~cjlin/libsvm/
before training SVM we have normalized features to [0,1] in the following way:
%normalization between [0,1]

massimo=max(TR)+0.00001;%max value training set

minimo=min(TR);%min value test set

training=[];

test=[];

for i=1:size(TR,2)%for all the features

    training(1:size(TR,1),i)=double(TR(1:size(TR,1),i)-minimo(i))/(massimo(i)-minimo(i));
    
end

for i=1:size(TE,2)%for all the features

    test(1:size(TE,1),i)=double(TE(1:size(TE,1),i)-minimo(i))/(massimo(i)-minimo(i));
    
end


the fusion among the different classifiers is very simple, we sum the scores. 
