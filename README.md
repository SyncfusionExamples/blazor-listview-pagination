# Blazor ListView with Pagination

## Project Overview
This sample demonstrates how to add pagination to the Syncfusion [Blazor ListView](https://www.syncfusion.com/blazor-components/blazor-listview) component by integrating it with an external Pager. The application displays nine locally defined vehicle records in groups of three and updates the visible records when users navigate between pages. A custom data adaptor processes each paging request so that the ListView displays only the records associated with the selected page.

## Features
- Uses the Syncfusion Blazor `SfListView` component to display vehicle records in a paginated list.
- Maps the `Text` and `Id` fields of each `VehicleData` record through `ListViewFieldSettings`.
- Connects the ListView to `SfDataManager` using `CustomAdaptor` and `Adaptors.CustomAdaptor`.
- Creates the initial `DataQuery` with `Query.Take(3)` to display the first three records.
- Uses the Syncfusion Blazor `SfPager` component to provide page-based navigation.
- Sets `PageSize` to `3` so that the Pager and ListView use the same number of records per page.
- Calculates `TotalItemsCount` from `Vehicles.Count` so that the Pager represents all nine records.
- Handles the `PageChanged` event through the `click` method when users select another page.
- Calculates the record offset with `(CurrentPage - 1) * 3` and updates the query using `Skip` and `Take`.
- Defines the local data through the `VehicleData` model and the static `Vehicles` collection.
- Implements `CustomAdaptor.Read` to receive and process each `DataManagerRequest`.
- Applies the requested data operations to the local collection through `DataOperations.Execute<VehicleData>`.
- Returns a `DataResult` containing the processed records and total record count when `RequiresCounts` is enabled.

## Prerequisites
Ensure the following requirements are met before running this project:
- Visual Studio 2022 or Visual Studio Code
- .NET SDK compatible with Blazor

## How to run the project
**Visual Studio 2022**

1. Clone or download this repository.
2. Open the solution file:

   `ListViewWithPagination.sln` 

3. Restore the NuGet packages by rebuilding the solution.
4. Set the startup project to:

   `ListViewWithPagination`

5. Build the solution.
6. Run the application using `Ctrl+F5`.
7. Open the application URL displayed by Visual Studio after launch.
8. Verify that the ListView displays three vehicle records and that the Pager navigates through all three pages.

**Visual Studio Code**

1. Clone or download this repository.
2. Open the repository folder in Visual Studio Code.
3. Open the integrated terminal.
4. Navigate to the project directory:

```bash
cd blazor-listview-pagination
```

5. Restore the NuGet packages:

```bash
dotnet restore
```

6. Run the project:

```bash
dotnet run
```

7. Open the local URL displayed in the terminal after the application starts.
8. Verify that the ListView displays three vehicle records and that the Pager navigates through all three pages.

## Support and Feedback

- For general product questions, visit the [Syncfusion Community Forum](https://www.syncfusion.com/forums) or [Syncfusion Support](https://www.syncfusion.com/support).
- To report an issue specific to this sample, open a GitHub issue in this repository.
- Official documentation: [Blazor ListView getting started documentation](https://blazor.syncfusion.com/documentation/listview/getting-started)

## License

This is a Syncfusion sample project provided to demonstrate product usage. Review the [Syncfusion license terms](https://www.syncfusion.com/sales/pricing?category=ui-components) before using Syncfusion components in your own applications.