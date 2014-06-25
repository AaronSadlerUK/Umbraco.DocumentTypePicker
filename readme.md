# RB: Document Type Picker

The Document Type Picker package allows editors to choose a list of Document Types to be saved against a content page. This could be used for things like site map exclusions or navigation lists.

## Set Up

Create a new data type using the RB.DocumentTypePicker property editor. Add a new property to a document type using the new data type you have just created. Once you have created your new property, you should be able to choose from a list of current document types present within your Umbraco solution.

## Converter

When using a property value on a template, add the following code to create a strongly type version of the key value editor property value.

    @{
        IEnumerable<string> documentTypes = CurrentPage.GetPropertyValue<IEnumerable<string>>("alias");
    }
	
Once converted, you will be able to choose single items and loop through each. For example:

    @{
        // Loop through each alias
        foreach (var documentType in documentTypes)
        {
            @documentType;
        }
    }

## Contributing

To raise a new bug, create an [issue](https://bitbucket.org/rbdigital/umbraco-documenttype-picker/issues) on the Bitbucket repository. To fix a bug or add new features or providers, fork the repository and send a [pull request](https://bitbucket.org/rbdigital/umbraco-documenttype-picker/pull-requests) with your changes. Feel free to add ideas to the repository's [issues](https://bitbucket.org/rbdigital/umbraco-documenttype-picker/issues) list if you would to discuss anything related to the package.

## Publishing

Remember to include all necessary files within the package.xml file. Run the following script, entering the new version number when prompted to created a published version of the package:

    Build\Release.bat

The release script will amend all assembly versions for the package, build the solution and create the package file. The script will also commit and tag the repository accordingly to reflect the new version.