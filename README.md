# IEC-CIM-in-OWL
experimental  attempt to to express IEC CIM in the Web Ontology Language in accordance to the UML to 
OWL transformation suggested by the OMG ODM specification. Transformation is done manually

# copy right notice
(identical to the IEC-CIM UML model) 
The entire work provided in the UML project file is dedicated to the public domain.  
As such, it is not, has not, and will not be copyrighted by any individual, entity or organization.


# Motivation: 
The web ontology is a much more expressive and formal language for information models compared
to UML class diagrams. However, modelling logic differs between Object Orientation (UML) and OWL-Ontologies
to such an extend that automatic transformation is not sensible. This is an experiment to gain experience in
the finer points of OO and Ontology modelling and their relationship.


# Things to keep in mind 
1) These ontologies are incomplete, especially ObjectProperties are likely to be missing. Refer to the IEC-CIM UML 
model for a complete picture of the information standard.
2) Feel free to contribute missing packages or concepts. However, pleas contact me first as I am still working on the method

# Method
Manually recreate IEC-CIM concepts in Protégé according to UML-> OWL transformation as suggested by the OMG ODM specification.

- UML Package          ->   Ontology (separate files, use imports for cross package references)
- UML Class            ->   OWL class
- UML Attribute        ->   primitives: Data Property
                       ->   Complex/CIM data types: Object Property
- UML Association      ->   Object Property 
- UML enumerated class ->   Owl class with instances (owl:oneOf, see https://stackoverflow.com/questions/28004964/using-owloneof-in-protege for method)
- UML specialization   ->   owl:subclass


# Naming Conventions
- Classes                                             -> ClassName
- attributes (whatever their representation in OWL)   -> ClassName.attributeName 
- enumerated individual                               -> ClassName.individualNameN
- associations                                        -> AssociciationName 

Note: unfortunately IEC-CIM is not consistently unique in its attribute- enumeration-, and association naming. This means tha
In case of attribute and enumeration naming prefising the ClassName is necesary to ensure uniqueness. In the case of association names 
this means that for now the `inverse of' property is not supported 
