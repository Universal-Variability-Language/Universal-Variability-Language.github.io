### Community-Driven Language for Variability Models

The **U**niversal **V**ariability **L**anguage is a community effort towards a unified language for variability models. UVL is a direct result of the efforts within the <a href="https://modevar.github.io/">MODEVAR</a> initiative. *Do you have any questions on UVL?* *Do you want to contribute?* *We gladly receive your message at [Contact](mailto:chico.sundermann@uni-ulm.de).*


# Language Design

UVL specifies variability models with a tree-like structure to represent the hierarchical structure of variability models. Below you can see a simple example of a variability model in UVL. The tree structure is visualized on the right side in the [FeatureIDE](https://github.com/FeatureIDE/FeatureIDE) representation. The language core of UVL comes with several concepts to specify constraints:

* *Mandatory*: The feature needs to be selected if its parent is selected
* *Optional*: The feature can be selected if its parent is selected
* *Or*: At least one of the children need to be selected if its parent is selected
* *Alternative*: Exactly one of the children needs to be selected
* *Cross-tree constraints*: Arbitrary propositional constraints over the features 

<img align="right" src="pics/small_sandwich.png" alt="Small Sandwich" width="300">
<pre>
<code>
<b>features</b>
    Sandwich
        <b>mandatory</b>
            Bread
        <b>optional</b>
            Sauce
                <b>alternative</b>
                    Ketchup
                    Mustard
            Cheese
constraints
    Ketchup => Cheese
</code>
</pre>

# Software

### Tool Support for UVL
* Java-based parser for UVL: <a href="https://github.com/Universal-Variability-Language/uvl-parser2.0">UVL-Parser2.0</a>
* Python-based parser for UVL (WIP): [UVL Parser](https://github.com/flamapy/uvlparser) 
* Rust-based Language Server Protocol for integrating UVL in your favorite IDE:  <a href="https://github.com/Universal-Variability-Language/uvl-lsp">UVLS</a> 
* Visual Studio Code <a href="https://marketplace.visualstudio.com/items?itemName=caradhras.uvls-code">extension </a> based on **UVLS**

### Tools Integrating UVL

* IDE for feature-oriented software development: <a href="https://github.com/FeatureIDE/FeatureIDE">FeatureIDE</a>
* Python-based analysis frame for variability models: [Flama](https://github.com/flamapy/)
* Transformations between different variability modelling approaches: [TraVarT](https://github.com/SECPS/TraVarT)


# Publications
Here, we only present a small selection of papers. Any interesting work on UVL missing? We are happy to embed your suggestion. [Contact](mailto:chico.sundermann@uni-ulm.de)

### Work on UVL

* Chico Sundermann, Kevin Feichtinger, Dominik Engelhardt, Rick Rabiser, and Thomas Thüm. 2021. Yet another textual variability language? a community effort towards a unified language. SPLC '21. https://doi.org/10.1145/3461001.3471145
* Chico Sundermann, Tobias Heß, Dominik Engelhardt, Rahel Arens, Johannes Herschel, Kevin Jedelhauser, Benedikt Jutz, Sebastian Krieter, and Ina Schaefer. 2021. Integration of UVL in FeatureIDE. MODEVAR@SPLC '21. https://doi.org/10.1145/3461002.3473940
* Kevin Feichtinger, Johann Stöbich, Dario Romano, and Rick Rabiser. 2021. TRAVART: An Approach for Transforming Variability Models. VaMoS '21. https://doi.org/10.1145/3442391.3442400
* Dario Romano, Kevin Feichtinger, Danilo Beuche, Uwe Ryssel, and Rick Rabiser. 2022. Bridging the gap between academia and industry: transforming the universal variability language to pure::variants and back. MODEVAR@SPLC '22. https://doi.org/10.1145/3503229.3547056

### Work Relevant for the Design of UVl
* Maurice H. ter Beek, Klaus Schmid, and Holger Eichelberger. 2019. Textual Variability Modeling Languages: An Overview and Considerations. MODEVAR@SPLC '19.
* Thorsten Berger and Philippe Collet. 2019. Usage Scenarios for a Common Feature Modeling Language. MODEVAR@SPLC '19. https://doi.org/10.1145/3307630.3342403