---
title: 👨‍💻 Filozofia programowania
description: Moje opinie na wybrane tematy związane z programowaniem
---

# ✨ Programming Philosophy

> Simplicity is a key to better maintainability.

## ORMy

Nie przepadam za rozbudowanymi ORMami. Wolę query buildery, są bliżej SQLa, a co za tym idzie, można szybko zacząć korzystać z potęgi SQL. Ludzie często wybierają ORM, bo nie chcą tracić czasu na SQL. Do apki typu hello world to wystarczy, ale gdy chcemy wyciągnąć większą ilość danych (i nie daj Boże przeliczyć coś *w locie*) to zaczynają sie problemy. Więc deweloperzy sięgają po HQL czy jakiś inny badziew dołączany do ORM'a. A finalnie i tak mogą nie osiągnąć tego co chcieli. Query nie zwraca tego co powinno, performance leży, a wygenerowany SQL to crap. Nie uczcie się ORMów, uczcie się SQLa!

Moim ulubionym combo jest [knex](https://knexjs.org/) + [objection](https://vincit.github.io/objection.js/). Moje zdanie praktycznie pokrywa się z tym [wpisem](https://blog.logrocket.com/why-you-should-avoid-orms-with-examples-in-node-js-e0baab73fa5/).

## TS

Wśród developerów często panuje przeświadczenie *jeśli znasz JavaScript, możesz łatwo przerzucić się na TypeScript*. TS to JS ulepszony o typy, no to jazda z przepisywaniem do apki do TS! O nie, nie tak szybko. Zanim zaczniesz cokolwiek pisać zastanów się nad tymi rzeczami:

- typowanie explicite i implicite (z tego pierwszego chcemy korzystać, gdy już naprawdę nie mamy wyjścia (poza paroma wyjątkami 🙃)),
- typy jako zbiory,
- type guardy i control flow analysis,
- typy wbudowane,
- tooling (pakowanie, eslint, wsparcie yarn berry etc.),
- zaawansowany TS (exhaustive checks, discriminated unions etc.)
- pułapki i ograniczenia TS,

dodatkowo:

- co da Ci wprowadzenie typów do projektu? Jeśli codebase jest ogromny, ale jest porządnie otestowany i nie ma potrzeby zmian/rozwoju, to dodanie typów tylko WOW TYPY jest bezsensu,
- czy jesteś w stanie przygotować **cały** tooling? Pamiętaj o Dokerze i CI,
- czy zespół pracujący w projekcie zna TS na wystarczająco dobrym poziomie?

Jeśli na którykolwiek z tych punków nie jesteś przygotowany, raczej nie jesteś gotowy na TS.

## Error handling

Obsługa błędów powinna być  first-class citizen w każdej apce. Szczególnie w tych opartych na JS, gdzie rzucona może zostać nawet emotikona jednorożca 🦄. Zazwyczaj musi iść w parze z odpowiednim monitoringiem (np. Sentry).

## Performance

> premature optimization is the root of all evil

Ten cytat Tony Hoare'a, pupularyzowany przez Donalda Knutha, to jedna z najważniejszych dobrych praktyk. Optymalizacja wydajności nie jest łatwa. Przy optymalizacji nie można opierać się na intuicji. *O teraz się chyba szybciej załadowało. Działa.* Zawsze trzeba mieć jakiś miernik. Dla frontendu to mogą być devtoolsy i lighthouse, dla backendu, w zależności od problemu, średni czas requestu dla wielu wywołań, jakieś dane z dashboardu Kubernetesa.

## Battle-tested solutions

Jaranie sie nowymi trendami nie jest dobre. Podoba mi się stwierdzenie, że za każdym razem jak powiesz *biblioteka JS*, w npm registry została dodana nowa libka 🙂. Ostatnio (grudzień 2021) stanąłem przed wyzwaniem. Musiałem zmigrować legacy frontend napisany w HBS, w którym ciężko już się pisało, do czegoś innego. Miałem ten przywilej, że mogłem wybrać co chcę. SvelteKit, coś z Tailwindem, czy może nowość od Shopify - Hydrogen? Nic z tych rzeczy. Wybrałem NextJS + MUI. Najstarszego z wyżej wymienionych, ale też najpopularniejszego i najlepiej wspieranego. Praktycznie każdy problem do wygooglowania, wiele dobrych praktyk itd.

## Motywacja

Przespanie się z problemem, pójść pobiegać, rozmowa z innymi devami - to wszystko spoko, ale nic tak nie motywuje jak Steve Ballmer skandujący: DEVELOPERS, DEVELOPERS, DEVELOPERS... !

{% embed url="https://www.youtube.com/watch?v=Vhh_GeBPOhs" %}
