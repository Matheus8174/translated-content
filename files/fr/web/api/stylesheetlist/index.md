---
title: StyleSheetList
slug: Web/API/StyleSheetList
tags:
  - API
  - CSSDOM
  - NeedsContent
  - NeedsUpdate
translation_of: Web/API/StyleSheetList
---
<p>{{APIRef("CSSOM")}}</p>

<p>L'interface StyleSheetList représente une liste de {{domxref("StyleSheet")}}.</p>

<p>Il s'agit d'un objet de type array, mais qui ne peut pas être itéré à l'aide de la méthode {{jsxref("Array")}}. Il peut néanmoins être itéré dans une boucle {{jsxref("Statements/for", "for")}} standard en utilisant ses indices, ou converti en un {{jsxref("Array")}}. </p>

<h2 id="Example">Exemple</h2>

<pre class="brush: js">// Récupère toutes les règles CSS du document en cours en utilisant les méthodes de Array
var allCSS = [].slice.call(document.styleSheets)
                     .reduce(function (prev, styleSheet) {
        if (styleSheet.cssRules) {
            return prev +
                [].slice.call(styleSheet.cssRules)
                        .reduce(function (prev, cssRule) {
                    return prev + cssRule.cssText;
                });
        } else {
            return prev;
        }
    });</pre>