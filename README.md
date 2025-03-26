# Sintija – Apģērbu E-commerce Tērzēšanas Bots

## Projekta Apraksts
"Sintija" ir tērzēšanas bots, kas izstrādāts apģērbu e-commerce veikalam.
- atrast un iegādāties apģērbu, 
- personalizēti ieteikumi, 
- akciju informācija

## Funkcionalitātes
Uzdevuma kritēriji:
- **Trīs dažādu entitāšu atbalsts:**
  1. **Produkti:** (piemēram, "T-krekli", "Bikses", "Aksesuāri")
  2. **Stili:** (piemēram, "Klasisks", "Moderns", "Sportisks")
  3. **Akcijas:** (piemēram, "Izpārdošana", "Atlaide", "Jaunie izstrādājumi")
- **Nejaušu atbilžu izmantošana:** Dinamisku akciju piedāvājumi, kas tiek atlasīti nejauši.
- **Divu līmeņu sazarošanās:** Minimāli  četri dialoga posmi – datu ievākšana un personalizēta atbilde.
- **Lietotāja datu saglabāšana un izmantošana:** Saglabā izvēlētos datus, lai nodrošinātu personalizētus ieteikumus.
- *(Papildpunktu iespēja: realizēt bots arī citā platformā, piemēram, izmantojot Pandorabots.)*

## Dialoga Plūsma

### 1. Lietotāja Sagaidīšana
Bots sveic lietotāju un prasa izvēlēties apģērbu kategoriju.

### 2. Produkta Kategorijas Izvēle
- **Entitāte:** Produkta kategorija  
  **Piemēri:** "T-krekli", "Bikses", "Aksesuāri"  
Bots saglabā lietotāja izvēli.

### 3. Stila Preferences Iegūšana
Bots prasa lietotāja stila izvēli, lai varētu sniegt pielāgotus ieteikumus.

### 4. Akciju Piedāvājumu Prezentēšana
Izmantojot saglabātos datus, bots piedāvā nejaušus akciju piedāvājumus, piemēram, atlaides vai jaunākās kolekcijas.

### 5. Noslēguma Saziņa
Bots jautā, vai lietotājam vēl ir kādi jautājumi vai nepieciešama papildu palīdzība.

## Koda Paraugs Chatfuel Blokiem (JSON)

### Bloks: Lietotāja Sagaidīšana
```json
{
  "messages": [
    {
      "text": "Sveiki, es esmu Sintija – Tava apģērbu veikala asistente! Kāda apģērbu kategorija Tevi interesē? (T-krekli, Bikses, Aksesuāri)"
    }
  ],
  "actions": [
    {
      "set_attributes": {
        "category": "{{user_input}}"
      }
    },
    {
      "redirect_to_blocks": ["Stila Preferences"]
    }
  ]
}
