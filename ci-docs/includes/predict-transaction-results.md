---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611097"
---
- **Ydeevne for træning af model**: Klassificeringerne A, B eller C angiver resultatet af forudsigelsen og kan hjælpe dig med at træffe beslutning om at bruge de resultater, der er gemt i outputobjektet.

  Vurderingerne bestemmes ud fra følgende regler:
  - **A**, når modellen forventes at forudse mindst 50 % af de samlede forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er afgået, er større end den oprindelige sats, med mindst 10 %.
  - **B**, når modellen forventes at forudse mindst 50 % af de samlede forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er afgået, er op til 10 % større end den oprindelige sats.
  - **C**, når modellen forventes at forudse mindre end 50 % af de samlede forudsigelser, eller når procentsatsen for præcise forudsigelser for kunder, der er afgået, er mindre end den oprindelige sats.
  - **Oprindelig plan** tager forudsigelsestidsvinduets input for modellen (f. eks. et år), og modellen opretter forskellige brøkdele af tiden ved at dividere den med 2, indtil den er på en måned eller mindre. Disse brøker bruges til at oprette en forretningsregel for kunder, der ikke har købt i denne tidsramme. Disse kunder betragtes som afgået. Den tidsbaserede forretningsregel med den højeste mulighed for at forudse, hvem der sandsynligvis afgår, vælges som oprindelig plan.

- **Sandsynlighed for afgang (antal kunder)**: Kundegrupper baseret på deres forudsagte risiko for afgang. Du kan også [oprette kundesegmenter](../prediction-based-segment.md) med stor risiko for afgang. Sådanne segmenter hjælper dig med at forstå, hvor din grænse skal være for segmentmedlemskab.

- **Mest indflydelsesrige faktorer**: Der er mange faktorer, som tages i betragtning ved oprettelsen af din forudsigelse. Hver af faktorerne er vigtig for de aggregerede forudsigelser, som en model opretter. Brug disse faktorer til at validere dine forudsigelsesresultater. Eller brug oplysningerne senere til at [oprette segmenter](../prediction-based-segment.md), der kan være med til at påvirke risikoen for kundeafgang.