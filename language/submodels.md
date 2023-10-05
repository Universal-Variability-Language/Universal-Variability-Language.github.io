### Importing Submodels

Larger variability models may be hard to overview. To simplify viewing and editing such models, UVL allows specifying submodels that can then be referenced in a composing model.

Consider our sandwich model as example:

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
<b>constraints</b>
    Ketchup => Cheese
</code>
</pre>

Here, it may make sense to decompose the Sauce into a separate UVL model:

<pre>
<code>
<b>features</b>
    Type
        <b>alternative</b>
            Ketchup
            Mustard
</code>
</pre>

Suppose we stored this submodel in a path ./submodels/Sauces.uvl

We can then use this submodel by using the **imports** keyword in a composed model. Further, we can reference the root feature of the imported model at any point the feature tree.

<pre>
<code>
<b>imports</b>
    submodels.Sauces as Sauce

<b>features</b>
    Sandwich
        <b>mandatory</b>
            Bread
        <b>optional</b>
            Sauce.Type
<b>constraints</b>
    Sauce.Ketchup => Cheese
</code>
</pre>