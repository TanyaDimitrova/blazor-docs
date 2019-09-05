---
title: Orientation
page_title: Menu for Blazor | Orienatation
description: Orientation on the Menu for Blazor
slug: components/menu/orientation
tags: telerik,blazor,menu,events
published: true
position: 10
---

# Orientation

You can control the orientation of the Menu for Blazor so that it orders its items horizontally or vertically.

The default orientation is horizontal.

>caption Changing the orientation of a menu

![](images/menu-change-orientation.gif)

>caption Set orientation

````CSHTML
@using Telerik.Blazor.Components.Menu
@using Telerik.Blazor

<select @bind=@orientation>
    <option value=@MenuOrientation.Horizontal>Horizontal</option>
    <option value=@MenuOrientation.Vertical>Vertical</option>
</select>

<TelerikMenu Data="@MenuItems" Orientation="@orientation">
</TelerikMenu>

@code {
     MenuOrientation orientation;

    public List<MenuItem> MenuItems { get; set; }

    public class MenuItem
    {
        public string Text { get; set; }
        public string Icon { get; set; }
        public List<MenuItem> Items { get; set; }
    }

    protected override void OnInitialized()
    {
        MenuItems = new List<MenuItem>()
        {
            new MenuItem()
            {
                Text = "Share",
                Icon = IconName.Share,
                Items = new List<MenuItem>()
                {
                    new MenuItem()
                    {
                        Text = "FaceBook",
                        Icon = IconName.Facebook
                    },
                    new MenuItem()
                    {
                        Text = "LinkedIn",
                        Icon = IconName.Linkedin
                    },
                    new MenuItem()
                    {
                        Text = "Twitter",
                        Icon = IconName.Twitter
                    },
                }
            },
            new MenuItem()
            {
                Text = "Map Location",
                Icon = IconName.MarkerPin
            }
        };

        base.OnInitialized();
    }
}
````


## See Also

* [Menu Overview]({%slug components/menu/overview%})
* [Live Demo: Orientation](https://demos.telerik.com/blazor-ui/menu/orientation)