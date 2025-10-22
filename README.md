# how-to-disable-the-ripple-effect-in-.net-maui-expander

This short guide shows how to disable (or customize) the ripple/tap background effect that appears on Syncfusion's SfExpander header in a .NET MAUI app. The sample project included in this repository demonstrates a simple, production-friendly approach that keeps the Expander header visuals intact while removing the default ripple highlight that may be undesirable for certain designs.

Why you might want to disable the ripple
- Visual consistency: Some designs require a flat, static header without transient touch feedback.
- Accessibility: In some scenarios the ripple obscures icons or text during animation.
- Cross-platform parity: Native tap feedback differs across platforms; removing it can unify appearance.

To learn more about these features, check out the official user guide:
- [Getting Started with SfExpander](https://help.syncfusion.com/xamarin/expander/getting-started)

What this sample does
- Shows how to set theme resources so the Expander header ripple background becomes transparent.
- Keeps the regular header layout, icons and labels unchanged.
- Works across supported MAUI platforms (Android, iOS, MacCatalyst, WinUI) where Syncfusion.Maui.Expander is supported.

## XAML

Snippet from MainPage.xaml (resource setup)

```
<ContentPage.Resources>
	<syncTheme:SyncfusionThemeDictionary>
		<syncTheme:SyncfusionThemeDictionary.MergedDictionaries>
			<ResourceDictionary>
				<x:String x:Key="SfExpanderTheme">CustomTheme</x:String>
				<Color x:Key="SfExpanderHeaderRippleBackground">Transparent</Color>
			</ResourceDictionary>
		</syncTheme:SyncfusionThemeDictionary.MergedDictionaries>
	</syncTheme:SyncfusionThemeDictionary>
</ContentPage.Resources>
```

Relevant part of the Expander header and content

```
<syncfusion:SfExpander AnimationDuration="200" IsExpanded="True" >
	<syncfusion:SfExpander.Header>
		<Grid>
			<Grid.RowDefinitions>
				<RowDefinition Height="48"/>
			</Grid.RowDefinitions>
			<Grid.ColumnDefinitions>
				<ColumnDefinition Width="35"/>
				<ColumnDefinition Width="*"/>
			</Grid.ColumnDefinitions>
			<Label Text="&#xe703;" FontSize="16" Margin="14,2,2,2"
					   FontFamily='{OnPlatform Android=AccordionFontIcons.ttf#,WinUI=AccordionFontIcons.ttf#AccordionFontIcons,MacCatalyst=AccordionFontIcons,iOS=AccordionFontIcons}'
					   VerticalOptions="Center" VerticalTextAlignment="Center"/>
			<Label CharacterSpacing="0.25" FontFamily="Roboto-Regular"  Text="Invoice Date" FontSize="14" Grid.Column="1" VerticalOptions="CenterAndExpand"/>
		</Grid>
	</syncfusion:SfExpander.Header>
	<syncfusion:SfExpander.Content>
		<Grid Padding="18,8,0,18" >
			<Label CharacterSpacing="0.25" FontFamily="Roboto-Regular"  Text="11:03 AM, 15 January 2019" FontSize="14" VerticalOptions="CenterAndExpand"/>
		</Grid>
	</syncfusion:SfExpander.Content>
</syncfusion:SfExpander>
```

How it works (short)
- The Syncfusion theme dictionaries expose tokens (resource keys) that control colors and brushes used by controls.
- `SfExpanderHeaderRippleBackground` is the token used by the Expander header's pressed/tapped visual.
- Setting it to `Transparent` removes the visible ripple while leaving the Expander interactive.

##### Conclusion
 
I hope you enjoyed learning about how to disable the ripple effect in Xamarin.Forms Expander (SfExpander).
 
You can refer to our [Xamarin.Forms Expander feature tour page](https://www.syncfusion.com/xamarin-ui-controls/xamarin-expander) to know about its other groundbreaking feature representations and [documentation](https://help.syncfusion.com/xamarin/expander/getting-started), and how to quickly get started for configuration specifications.

For current customers, you can check out our components from the [License and Downloads](https://www.syncfusion.com/sales/ui-component-suite) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads) to check out our other controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums/) or [Direct-Trac](https://support.syncfusion.com/create). We are always happy to assist you!