# Diagram for retail tech's APIs and there environment

**Warning** : *This documentation is currently a **work in progress** and will be subject to many changes until the v1.*

*If you want **help** or **advices** to start your API, please send us a message.* 

This diagram as for purpose to simplify, to organize and to normalize data, documentations, calls and other common elements associated to an API.

## Summary 

- **[Good practices](#good-practices)**
- **[Getting started](#getting-started)**
- **[Data diagram](#data-diagram)**
- **[API structure](#API-structure)**
- **[Documentation look](#documentation-look)**
- **[Participate](#participate)**
- **[Actuality](#actuality)**
- **[Authors](#authors)**
- **[License](#license)**
- **[Acknowledgments](#aknowledgments)**

## <a name="good-practices"></a> Good practices

- Save the version number of the diagram somewhere (generally near the mention of this repository), whit a status (example : v1 to v1.3 in progress)
- Don't modify your database. Create a middleware which will transform the data from your database to the correct output (and reverse)
- Check frequently the actuality

## <a name="getting-started"></a> Getting started

Check the **example repository** to have an idea of what the documentation will look like at the v1.

The v1 will contains a repository named "*getting-started*", which will looks like the "*validated*" repository and will include :
- Basic JSON diagram for most common data
- Link to the most basic documentation tools
- More detailed documentation tools explanation
- Documented common request associated to the data

## <a name="data-diagram"></a> Data diagram

The data diagram has for purpose to help you organize the data you get and you post.

It serves as a base for communication, by definning a norme with the change you put in data.

The data diagram follows simple, but strict rules :

- Explicit field name
- Definition of the data
  - SQL type (string, integer, boolean, date (dd-mm-YYYY HH:ii:ss), )
  - Mandatory take a "*" at the end
  - If in array, surround the data definition by "[]"
  - Unique tell if the field should be unique
  - Auto-increment  tell if the field with increment alone
- Encapsulate group of data in related object
- To extend another object (for example product to food), add the field "extand at the top of the object.


example :

```json
{
  "extand": "another object",
  "id": "integer unique auto-increment *",
  "personnal_data": {
    "name": {
      "firstname": "string",
      "lastname": "string unique *"
    },
    "addresses": [{
      "address1": "..."
    }]
  }
}
```

## <a name="API-structure"></a> API structure

The API structure will help you choose a name, method, url, header and parameters so it allow you to go **straight to programmation**.

Later, it'll also propose **good practices** around pagination, real time, data selection, and other. 

It should look something like :

```json
{
    "resource": "resource-cluster_resource",
    "methods": ["GET", "POST", "PUT", "DELETE"],
    "url": "https://api.domaine.name/resource_cluster/resource/:id",
    "parameters": {"id": 3, "params": {"param1": "data", "param2": "data"}},
    "header": {"header1": "element1", "header2": "element2"},
    "remove_field_response": {"get": ["field_to_remove"]}
}
```

As you can see, we don't put the answer in. The name and the url should indicate the position of the returned resource, and the returned resource should be the response or the resource affected by the changes.

## <a name="documentation-look"></a> Documentation look

The documentation look will advise you about how to build a smart, beautiful documentation, and recommend you tools associated with the size of your API, but also the type and the form it took.

At the beginning, it will simply be a markdown file listing some API/tools with pictures and descriptions. In the future, it would be good to have advice on colors, font, size, but also on content (CLIs, multiples APIs, graph, etc).

## <a name="participate"></a> Participate

There is two ways to participate :
- **the correction**
- **the suggestion**

The first one is about modifying something wrong, like a syntax error, or update anything which need it, like a link, or something deprecated.

The suggestion as for purpose to let you propose something new, an modification or to remove something. For this, you need to:
- create (or update) a folder named with your username (or your organization name)
- add only useful folders reproducing the root structur
- includ only what you want to make suggestions about

***Why do we do like that ?***

This will allow us to know what each of you want or think important, to make a correlation and include the most present things to the base diagram.

In both cases, please :
- duplicate the repository
- make a change
- submit your pull request

## <a name="actuality"></a> Actuality

*2017-07-09* : This is brand new !! 

## <a name="authors"></a> Authors

Cédric PAUMARD - **Initial work** - *<a href="https://www.beamy.io" target="_blank">Beamy</a>*

See also the [list of contributors](#aknowledgments) who participated in this project.

## <a name="license"></a> License

This project is licensed under the MIT License - see the LICENSE file for details

## <a name="aknowledgments"></a> Acknowledgments

Hat tip to anyone who's code was used

