# Prototype d'équipe (branche temporaire)

> **À supprimer avant le 21 novembre.** Cette branche sert uniquement à l'équipe pour apprendre et tester. Le règlement impose que le code soit écrit le jour J : on recode tout de zéro ce jour-là, **sans copier-coller**.
>
> Commande de suppression, à lancer avant le 21 : `git push origin --delete prototype-equipe`

## Objectif

Disposer d'une application qui marche, pour tester chaque type d'utilisateur (client, client qui ne lit pas, cuisine, patronne, WhatsApp) et savoir exactement, le jour J :
- quelle stack et quelles dépendances installer ;
- comment fonctionnent la voix en dioula, l'IA qui transforme un message WhatsApp en commande, le paiement, l'impression du ticket.

## Stack

- **Next.js 16** (App Router, TypeScript, Tailwind 4) dans `app/`
- **Supabase en local** avec Docker (Postgres, temps réel)
- **Anthropic SDK** pour l'IA, avec un analyseur de secours par mots-clés quand il n'y a pas de clé `ANTHROPIC_API_KEY`
- **zod** pour valider les données, **lucide-react** pour les icônes

## État

Le socle Next.js est créé et les dépendances sont installées. Les écrans, la base de données et le mode d'emploi technique (`PLAYBOOK-TECHNIQUE.md`) arrivent dans les prochains commits.
