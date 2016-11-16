
# Contribute.Perl6.Org Web App

## Goal

Provide concise and easy steps for contributors to contribute to Perl 6
repositories and assets, to increase the amount and quality of contributions
made.

## Layout

While auxiliary features may be added in the future (e.g. Issue aggregator),
the main feature will be presented in a way of "flash cards" type of thing,
where the user is presented with large boxes containing very short descriptions
of what the user wishes to do. For example, the home page may be something like:


```
              Contribute to...

    +------+  +----------+  +-----------+
    | Docs |  | Websites |  | Marketing |
    +------+  +----------+  +-----------+
    +----------+ +-----------+  +--------------+
    | Compiler | | Ecosystem |  | I don't know |
    +----------+ +-----------+  +--------------+

    ｢Donate｣     ｢Need help? Chat with us｣
```

Say, the user clicks ｢Websites｣, the next screen will show:

```
    (𝘊𝘰𝘯𝘵𝘳𝘪𝘣𝘶𝘵𝘦 𝘵𝘰... ➡ 𝑾𝒆𝒃𝒔𝒊𝒕𝒆𝒔)

    +----------------+  +-----------+  +-------------------+
    | docs.perl6.org |  | perl6.org |  | modules.perl6.org |
    +----------------+  +-----------+  +-------------------+
    +------------------+  +------------+
    | design.perl6.org |  | rakudo.org |
    +------------------+  +------------+

    ｢Donate｣     ｢Need help? Chat with us｣
```

User clicks ｢modules.perl6.org｣:

```
    (𝘊𝘰𝘯𝘵𝘳𝘪𝘣𝘶𝘵𝘦 𝘵𝘰... ➡ 𝘞𝘦𝘣𝘴𝘪𝘵𝘦𝘴 ➡  
        𝙢𝙤𝙙𝙪𝙡𝙚𝙨.𝙥𝙚𝙧𝙡6.𝙤𝙧𝙜)

    +----------------+  +-------------------+
    | List my module |  | Solve open Issues |
    +----------------+  +-------------------+
    +---------------+  +----------------------+
    | Change design |  | I don't know / Other |
    +---------------+  +----------------------+

    -------------------------------------------

    ｢Repository｣ ｢Issues｣ ｢Install prereqs｣ ｢Build steps｣

    -------------------------------------------

    ｢Donate｣     ｢Need help? Chat with us｣
```

At this point the site will show some general info the user may wish to read
(like prereq build instructions), if the user clicks a specific "Recipe", like
｢Change design｣, the site will show more specific instructions, such us
*"styles are located in assets/sass; you need to install Mojolicious to run the
dev server"* and basically give the user all required info (like location of
files, or how they are built) as well as all the steps needed for them to
write, test, and submit their contribution.

## Content

The main goal of the site is being concise, so the instructions will be given
with the assumption the user is familiar with the technologies used, rather
than explaining how to, for example, install a Perl 5 module, or use `git`.

Pointers to such information may be provided as side tips that link to more
detailed guides, but in general very detailed instructions and edge cases are
best documented in CONTRIBUTING.md for a specific repo, to which this site will
link to

### "Recipes"

To make it easier to add and manage content, instructions for each type of work
done will be stored in a separate file. The file will be in MultiMarkdown
format, but augmented with a special header that will control how the recipe is
listed, as well as extra instructions to perform auxiliary functions.

For example, to include a recipe for how to change the design of the
modules.perl6.org a file can be created in:

```
    recipes
        └── websites
            └── modules.perl6.org
                └── change-design.md
```

The header of the file will contain the `title` and `location` fields:

```
% title: How to change the design of modules.perl6.org website
% location: Websites / modules.perl6.org / Change Design
```

The `location` controls which boxes show up that the user would need to click
to get to this recipe. So, starting from home page, they would need to click
"Websites", then "modules.perl6.org", then "Change design".

## Search / Accessibility

The site needs to provide at least some rudimentary search, so that one could
type, say, `nqp` and get all the recipes for NQP, or type `rakudo compile`
and find out how to compile Rakudo.

More importantly, the recipies need to be linkable, so that one could store
a URL to a specific recipe and then link a user directly to it.
