---
title: Nápoj jako komponenta
demand: 3
---

Abychom nakonec mohli zobrazit celou nabídku nápojů, budeme potřebovat, aby každý nápoj byl jedna komponenta. Podívejte se do `index.html` nebo do devtools na strukturu jednoho nápoje. Tento obsah si v `index.html` zakomentujte. Zakomentujte si také přidávání ingrediencí capuccina pomocí komponenty `Layer` v hlavním `index.js`.

1. Jak už jsme zvyklí, vytvořte pro komponentu složku `Drink` s `index.js` a `style.css`. Do `style.css` přesuňte styly související s komponentou. Pozor na to, že tentokrát ke stylu komponenty patří také obrázek `cup-selected.png`. Abychom měli vše hezky pohromadě, vytvořte ve složce komponenty složku `img`, do které tento obrázek přesuňte. (Dané styly musíte smazat nebo zakomentovat v hlavním `style.css`, protože tam bude obrázek `cup-selected.png` teď chybět).
1. V `index.js` vytvořte komponentu `Drink`, která očekává `props` v následujícím tvaru.

   ```js
   {
     id: 'romano',
     name: 'Romano',
     ordered: false,
     layers: [
       {
         color: '#fbdf5b',
         label: 'citrón',
       },
       {
         color: '#613916',
         label: 'espresso',
       },
     ],
     image: 'https://apps.kodim.cz/daweb/cafelora/assets/cups/romano.png',
   };
   ```

   Komponentu napište tak, aby vracela DOM element (vytvořený pomocí `document.createElement()`). Vnitřek komponenty můžete nastavit jako `innerHTML` tohoto prvku.

1. Uvnitř komponenty bude potřeba použít komponentu `Layer`. Dejte si pozor, abyse ji správně importovali.
1. Komponentu `Layer` v komponentě `Drink` vložíte do `innerHTML`, stejně jako jsme to dělali v hlavním `index.js`.
1. Název obrázku, který se má zobrazit, můžete vzít z vlastnosti `id`. Je potřeba pouze sestavit správnou cestu pro atribut `src` s použitím vlastnosti `id`.
1. Tlačítko zatím pouze zobrazte, fuknčnost mu přidáme v dalším kroku.
1. Zobrazte na stránce nápoj dle dat uvedených výše. V hlavním `index.js` na správný prvek použijte funkci `appendChild`, neboť naše komponenta vrací DOM element. Měli byste teď vidět jeden nápoj, *Romano*.
1. V této fázi si commitněte kód s užitečně napsanou commit zprávou a pushněte do vzdáleného repozitáře.