#   Binding-ItemsSource-for-the-SfComboBox-inside-template-column-in-Xamarin-DataGrid
Describes how to bind the ItemsSource from ViewModel for the SfComboBox loaded inside the template column in Xamarin.Forms DataGrid (SfDataGrid)

#  Getting Started with Xamarin ComboBox (SfComboBox)

##  Adding SfComboBox reference
You can add SfComboBox reference using one of the following methods:

## Method 1: Adding SfComboBox reference from nuget.org

Syncfusion Xamarin components are available in nuget.org. To add SfComboBox to your project, open the NuGet package manager in Visual Studio, search for Syncfusion.Xamarin.SfComboBox, and then install it.

##  Method 2: Adding SfComboBox reference from toolbox

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfComboBox control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to Toolbox.

##  Method 3: Adding SfComboBox assemblies manually from the installed location

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

#   Initializing ComboBox
Import the SfComboBox namespace in respective page as shown in the following code.

**[XAML]**

```
xmlns:combobox="clr-namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
```
Then initialize an empty combobox as shown in the following code,

**[XAML]**

```
<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
		<combobox:SfComboBox HeightRequest="40" x:Name="comboBox"/>
</StackLayout> 
```
#   Binding ItemsSource for the SfComboBox inside template column in Xamarin DataGrid
**[XAML]**
```
 <sfgrid:SfDataGrid x:Name="dataGrid"
                ItemsSource="{Binding State}" 
                       NavigationMode="Cell"
                               ColumnSizer="Auto"
                               SelectionMode="Multiple"
                            AutoGenerateColumns="True">
            <sfgrid:SfDataGrid.Columns>
                <sfgrid:GridTemplateColumn MappingName="Province">
                    <sfgrid:GridTemplateColumn.CellTemplate>
                        <DataTemplate>
                            <combobox:SfComboBox WidthRequest="150"
                                DataSource="{Binding StatesProvince,Source={x:Reference viewModel}}"></combobox:SfComboBox>
                        </DataTemplate>
                    </sfgrid:GridTemplateColumn.CellTemplate>
                </sfgrid:GridTemplateColumn>
            </sfgrid:SfDataGrid.Columns>
        </sfgrid:SfDataGrid>
```

## How to run this application?

To run this application, you need to first clone the Binding-ItemsSource-for-the-SfComboBox-inside-template-column-in-Xamarin-DataGrid repository and then open it in Visual Studio 2022. Now, simply build and run your project to view the output.

## <a name="troubleshooting"></a>Troubleshooting ##
### Path too long exception
If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.

## License

Syncfusion has no liability for any damage or consequence that may arise by using or viewing the samples. The samples are for demonstrative purposes, and if you choose to use or access the samples, you agree to not hold Syncfusion liable, in any form, for any damage that is related to use, for accessing, or viewing the samples. By accessing, viewing, or seeing the samples, you acknowledge and agree Syncfusion’s samples will not allow you seek injunctive relief in any form for any claim related to the sample. If you do not agree to this, do not view, access, utilize, or otherwise do anything with Syncfusion’s samples.
