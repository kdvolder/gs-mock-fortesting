gs-mock-fortesting
==================

Mock gs-guide to play around with codesets.json metadata.

A gs-xxx github project may include a '.codeset.json' file at 
the root of the project.

If no .codesets.json is found. The default will be assumed:

    [
        {
            "name": "initial",
            "dir": "initial"
        },
        {
            "name": "complete",
            "dir": "complete"
        }
    ]
    
A .codesets.json file should parse as an array of objects. Each object with
a 'name' and a 'dir' property. The 'dir' is interpreted as path relative
to the root of the github project it is contained within.

Common use cases:
-----------------

Projects that do not have any codesets that STS can import should put 
the following in '.codesets.json':

     []
        
Projects that have only one codeset that is 'the entire project' should put
the following in '.codesets.json':

     [{
         "name": "default",
         "dir": "."
     }]
     
Projects that have a code set that doesn't have build logic 
should exclude those codesets from STS imports.
This is because a codeset lacking build logic can not be imported 
into STS as a project. E.g. the "gs-gradle" has an initial codeset
that lacks build logic. Its ".codesets.json" declares that only the
"complete" code set is available on this guide as follows:

     [{
         "name" : "complete",
         "dir" : "complete"
     }]


