## Problem Statement

Food waste is a major problem in supermarkets, where perishable goods often expire without being sold. Managing stock efficiently while ensuring that customers receive fresh products is a challenging task. Traditional inventory systems rely on basic expiration tracking, but they often fail to significantly reduce waste or ensure regular stock rotation.

## Solution

To address this, we propose developing a **graph-based image analysis system** that can detect expired goods and provide intelligent suggestions for product placement within the supermarket. This system will utilize image inputs and graph algorithms to monitor inventory freshness and optimize shelf arrangements.

## Project Justification

This system will help streamline the process of monitoring stock by focusing only on products that need to be rotated or removed, saving time and effort. By modeling the relationships and dependencies between food items using graphs, we can minimize waste and improve inventory management in supermarkets.

## Technical Algorithms to Use

- **K-Nearest Neighbors (KNN) Graph**
- **Graph Clustering**

## Member Tasks

## Member 1 (AO Cushe)
Suggests similar food items based on name,shelf and features using K-NN graph.

## Member 2 (P Mabeso)
Classifies food items based on freshness levels using clustering techniques to group
them.

## Member 3 (MY Ntombela)
Building user-friendly GUI for supermarket employees and managers to visualize food
stock levels and make data informed decisions.

## Member 4 (TD Selane)
Tracks and updates food item freshness and expiry using its corresponding graph
representation and date metadata.

## How the Project Should Work

### Workflow Steps

1. **Image Upload**:  
   The user uploads one or more images of supermarket shelves.

2. **Region Selection**:  
   The GUI allows the user to crop or select regions of interest using a grid layout (e.g., 5x5 or 10x10 grayscale tiles).

3. **Graph Creation**:  
   For each selected region, the system converts the cropped region into a graph representation.

4. **Graph Comparison**:  
   The system compares the newly created graph with existing product graphs in the database.

5. **Classification**:  
   The system suggests the most likely product match based on visual similarity.

6. **User Feedback**:  
   If the classification is incorrect, the user can correct the match, and the system updates its learning model accordingly.

7. **Expiry Input**:  
   The user is prompted to input the expiry date for the correctly identified product.

8. **Graph & Metadata Linking**:  
   The product image is converted into a detailed graph:
   - Nodes represent products.
   - Edges represent spatial or visual relationships between products.
   - If multiple shelf images are used, the graph and metadata are linked to their respective images.

9. **Freshness Labeling**:  
   The system calculates the number of days remaining until expiry and assigns a freshness label:
   - `Fresh`
   - `Expires Soon` (within 2 days)
   - `Expired`

10. **KNN Matching**:  
    The system uses KNN to find and compare visually similar products from previous graphs.

11. **Graph Clustering**:  
    Products are grouped into clusters based on both visual similarity and freshness scores.

12. **GUI Display**:  
    The following are displayed (optional complexity):
    - Cropped product image
    - Graph visualization of the product (optional)
    - Expiry status
    - Table of all products in the inventory
    - Recommendations for which products should be rotated

13. **Repeat**:  
    The process is repeated for each product detected on the shelves.
