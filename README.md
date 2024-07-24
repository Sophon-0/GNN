# Link_Prediction_Hetero_CollecTRI_protein_sequence:

This script presents a comprehensive approach to link prediction in heterogeneous graphs using Graph Neural Networks (GNNs), specifically applied to biological data from CollecTRI. We predict TF target interactions, using protein sequence as node features. 

## Data Integration and Preprocessing: 
Utilizes CollecTRI, a database of gene regulatory interactions

## Graph Construction: 
Builds a heterogeneous graph structure using PyTorch Geometric's HeteroData object

## Transform and Split Data:
Split the edge data into training (80%), validation (10%), and testing (10%) edges using `RandomLinkSplit`.
Ensure negative samples (edges) are generated and added for evaluation.

## Model Architecture: 
Define a 2-layer Graph Neural Network (GNN) using `SAGEConv`. 
Create a classifier that applies the dot-product between source and destination node embeddings. 
Combine both the GNN and the classifier into a final heterogeneous model using `to_hetero`.

## Training Process: 
Implements mini-batch training using LinkNeighborLoader for efficient processing of large graphs
Implements a training loop: Uses Adam optimizer and binary cross-entropy loss.
Evaluation Metrics: Uses AUC as the primary performance metric
