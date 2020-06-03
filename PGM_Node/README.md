
There are 3 folders in PGM_Node:
  * Generate_XA_Data: To generate the graph data for the node classification experiments
  * Train_GNN_model: To train the GNN models for the  node classification tasks
  * Explain_GNN: To generate PGM Explaination for GNN predictions
  
To generate graph data, direct into Generate_XA_Data and run: 
`python3 GenData.py --dataset [dataset-name]` 

  * dataset-name: syn1, syn2, syn3, syn4, syn5, syn6, bitcoinalpha, bitcoinotc       
  * Generate feature matrix X, adjacency matrix A and ground-truth label L are stored in "XAL" folder

To generate ground-truth for explanations, direct into Generate_XA_Data and run: 
'python3 GenGroundTruth.py --dataset [dataset-name]'
  
  * dataset-name: bitcoinalpha, bitcoinotc       
  * Generated ground-truth Explanations are saved in "ground_truth_explanation" folder

To train GNN model, direct into Train_GNN_model and run:
'python3 train.py --dataset [dataset-name]'

  * dataset-name: syn1, syn2, syn3, syn4, syn5, syn6, bitcoinalpha, bitcoinotc
  * Generated model states are saved in "cpkt" folders
  * The model are obtained from https://github.com/RexYing/gnn-model-explainer

To run PGM explainer, direct into Explain_GNN folder and run:
'python3 main.py --dataset [dataset-name] --num-perturb-samples [int1] --top-node [int2]'
   
   * dataset-name: syn1, syn2, syn3, syn4, syn5, syn6, bitcoinalpha, bitcoinotc
   * int1: recommend 800-1000
   * int2: recommend None or 3,4,5
   * explanations are stored in result folder. Might need to creat 'dataset-name' folder to properly stored the result.

To evaluate explanations, direct into Explain_GNN folder and run:
'python3 evaluate_explanations.py --dataset [dataset-name] --num-perturb-samples [int1]
 
   * dataset-name: syn1, syn2, syn3, syn4, syn5, syn6, bitcoinalpha, bitcoinotc
   * reports are stored in result folder
