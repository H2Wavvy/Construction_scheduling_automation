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

# Collectives_identification

This Python function may be used to identify entity collectives (targeted at Truss-like collectives) in networks of structural entities within structures. 
The dependency graph and reverse dependency graph are obtained from the Graphing_Algorithm function in this repository.
While the entities_data input should be in a format:
entity_predictors = {
                'Name': Name, 
                'Edges': Edges,
                'Plan_Area': plan_area, 
                'Volume': Volume,  
                'Surface_Area': Surface_Area, 
                'BB_x': BB_x, 
                'BB_y': BB_y, 
                'BB_z': BB_z, 
                'Min_z': Min_z, 
                'Max_z': Max_z, 
                'Apect_Ratio_xy': Apect_Ratio_xy, 
                'Aspect_Ratio_Z': Aspect_Ratio_Z,  
                'Thickness_Proxy': Thickness_Proxy, 
                'Density': Density, 
                'No_faces':No_faces, 
                'is_WetTrade': WetTrade, 
                'is_HotTrade': HotTrade, 
                'Is_SurfaceConstruction': Is_SurfaceConstruction, 
                'is_collective': is_collective, 
                'is_prefabricated': is_prefabricated, 
                'No_dependance': No_dependance, 
                'No_dependants': No_dependant, 
                'Has_Predceding_Access': Has_Predceding_Access, 
                'Storey': Storey, 
                'is_installed': is_installed, 
                'Relative_elevation':Relative_elevation, 
                'Is_edge_object':Is_edge_object, 
                'is_masonry': is_masonry, 
                'is_steel': is_steel, 
                'is_Composite': is_Composite, 
                'is_concrete': is_concrete, 
                'is_rock': is_rock, 
                'is_timber': is_timber 
            }


# features_extraction 

This is a code used for obtaining the features for a structural entity, which are to be used for predicting the construction tasks and their durations for that entity. The inputs are the same as for the graphing_algorithm of 'Complete Entities Data' and 'Raw Geometric Data'. This is an extract from a far more sparse program, and so, more refinements may need to be carried out in order for it to be tested personally. 

