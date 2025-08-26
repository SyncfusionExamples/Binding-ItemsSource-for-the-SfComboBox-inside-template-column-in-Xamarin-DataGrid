#  How to bind the itemsSource of an SfComboBox inside a template column of a SfDataGrid.

This article demonstrates how to bind the `ItemsSource` of an `SfComboBox` inside a `GridTemplateColumn` of a `SfDataGrid` using the MVVM pattern in Xamarin.Forms.

The data displayed in the ComboBox within each row of the DataGrid is dynamically sourced from the ViewModel. To do this, we defined an ObservableCollection<string> named StatesProvince in the ViewModel, which holds the list of provinces. This collection is populated during the ViewModel's initialization. The ComboBox's DataSource property is bound to the StatesProvince collection.This ensures that each ComboBox in the grid rows has access to the same list of provinces defined in the ViewModel.

## Xaml#:

```xml
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