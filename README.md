# How to Implement Nested Grid Splitters in .NET MAUI

This repository contains a sample explaining how to implement nested Grid Splitters in .NET MAUI using the Syncfusion `SfGridSplitter` control.

Nested Grid Splitters enable developers to create complex and highly flexible layouts by placing one `SfGridSplitter` inside another. This approach is useful when applications require multiple resizable regions that can be adjusted independently. Common scenarios include dashboard applications, file explorers, development tools, management systems, and data analysis applications where users need precise control over the available screen space.

In this example, the primary Grid Splitter is configured with a vertical orientation, dividing the interface into a navigation pane on the left and a content area on the right. The content area contains another Grid Splitter configured with a horizontal orientation. This nested splitter further divides the space into Content and Details panes, allowing users to resize both sections independently.

By combining multiple Grid Splitters, developers can build sophisticated layouts while maintaining a consistent and intuitive user experience. The nested splitter automatically manages pane sizing and updates the layout dynamically when users drag any splitter.

## Sample

### XAML

```xml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:gridSplitter="clr-namespace:Syncfusion.Maui.GridSplitter;assembly=Syncfusion.Maui.GridSplitter"
             x:Class="GridSplitter.MainPage">

    <gridSplitter:SfGridSplitter Orientation="Vertical">

        <!-- Left Pane -->
        <gridSplitter:SplitterPane>
            <Border Background="#D6EAF8"
                    Padding="10">
                <Label Text="Navigation Pane"
                       HorizontalOptions="Center"
                       VerticalOptions="Center" />
            </Border>
        </gridSplitter:SplitterPane>

        <!-- Right Pane with Nested Splitter -->
        <gridSplitter:SplitterPane>

            <gridSplitter:SfGridSplitter Orientation="Horizontal">

                <gridSplitter:SplitterPane>
                    <Border Background="#D5F5E3"
                            Padding="10">
                        <Label Text="Content Pane"
                               HorizontalOptions="Center"
                               VerticalOptions="Center" />
                    </Border>
                </gridSplitter:SplitterPane>

                <gridSplitter:SplitterPane>
                    <Border Background="#FADBD8"
                            Padding="10">
                        <Label Text="Details Pane"
                               HorizontalOptions="Center"
                               VerticalOptions="Center" />
                    </Border>
                </gridSplitter:SplitterPane>

            </gridSplitter:SfGridSplitter>

        </gridSplitter:SplitterPane>

    </gridSplitter:SfGridSplitter>

</ContentPage>
```

## How It Works

The outer `SfGridSplitter` uses a vertical orientation to divide the page into two major sections:

- Navigation Pane
- Content Area

The Content Area contains another `SfGridSplitter` configured with a horizontal orientation. This nested Grid Splitter creates two additional panes:

- Content Pane
- Details Pane

As a result, the layout consists of three functional regions:

1. Navigation Pane
2. Content Pane
3. Details Pane

Users can interact with both splitters independently:

- The outer splitter resizes the Navigation Pane and Content Area.
- The inner splitter resizes the Content Pane and Details Pane.
- Layout updates occur automatically while dragging either splitter.
- Each pane can host any .NET MAUI view, including forms, charts, lists, images, and custom controls.

## Output

When the application runs, the following behavior can be observed:

- A navigation pane appears on the left side of the screen.
- A content area appears on the right side.
- The content area is further divided into Content and Details panes.
- The outer splitter can be dragged to resize the navigation section.
- The inner splitter can be dragged to resize the content and details sections.
- Both splitters work independently without affecting each other's functionality.
- Pane sizes update dynamically at runtime.
- The layout remains responsive across different screen sizes and orientations.

## Benefits of Nested Grid Splitters

Nested Grid Splitters provide several advantages for building advanced user interfaces:

- Create multi-level resizable layouts.
- Organize large amounts of content efficiently.
- Improve screen space utilization.
- Allow users to customize pane sizes based on their workflow.
- Support complex dashboard and workspace scenarios.
- Provide a desktop-like experience in .NET MAUI applications.
- Reduce the need for custom layout calculations.

## Common Use Cases

Nested Grid Splitters are particularly useful for:

- File explorer applications.
- Project management dashboards.
- Data analytics solutions.
- Reporting tools.
- Development environments.
- Administrative portals.
- Customer management systems.
- Monitoring and control dashboards.

## Conclusion

The Syncfusion `SfGridSplitter` makes it easy to implement nested resizable layouts in .NET MAUI applications. By placing one Grid Splitter inside another, developers can create rich and flexible interfaces that allow users to adjust multiple regions independently. This approach enhances usability, improves workspace organization, and helps build professional desktop-style applications across all supported .NET MAUI platforms.