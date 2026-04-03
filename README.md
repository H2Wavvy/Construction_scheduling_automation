# Construction_scheduling_automation
A repository containing all of the relevant algorithms designed and developed towards the research of an automated construction scheduling algorithm.

# ML_model_testing
This file contains the Python code which was used in order to optimise and test all relevant ML models for the regression and classification problems. 
To use this code, Github_ML_data.xlsx must be downloaded/saved to the directory in which the ML_model_testing code is being run from.  
Also, Github_ML_data.xlsx must be renamed in this directory to ML_Model_Data.xlsx.

# Graphing_Algorithm
This file contains the Python code of the graphing algorithm. This is an algorithm used to find the dependency between different entities of a structural model, where dependency here refers to whether entity A (e.g. steel beam) is structurally dependent, by load-pathing logics, on entity B (e.g. a RC wall). To test this code, it must be noted that for all structural entities in the model space 
This algorithm takes inputs: entities, structural_categories, and a dataframe.
It expects these structures: 

structural_categories = ['Build-up', 'Masonry built', 'Concrete built', 'Angle', 'Bar', 'Channel', 'Concrete beam', 'Concrete column', 'Gabion', 'Hollow section', 'Mesh', 'Metal board', 'Planed timber', 'Sawn timber', 'T section', 'Universal Beam', 'Universal Column']

Complete entities data = [{
'Name': Codified entity name,
'Dimensions': Bounding box dimensions,
'Volume': Volume,
'Surface Area': Surface area,
'Material/Product': Primary product used,
'Surface Product': Surface product used,
'Vertical Access Elements(Y/N)': Entity is used for vertical accessibility
}...More entities-> ]

Raw geometric data = [{
'Name': Codified entity name,
'Edges': Bounding box dimensions,
'Curved Faces': Definitions of curved faces,
'Planar Faces': Definitions of planar faces,
'Total Faces': Combined definitions of curved and planar faces       
}... More entities-> ]

To test this algorithm, you'll need to make significant modifications to the code. This is because the code is designed to be highly dependent on the code/s that came before it. As a suggestion, modify the code to remove the pre-processing and instead have an input of the 'processed' dictionary, making sure to gather codefied names for all the entities which match in that dictionary, and in the structural_names and architectural_names lists. 

