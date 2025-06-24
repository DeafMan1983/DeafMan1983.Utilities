# DeafMan1983.Utilities
DeafMan1983.Utilities is for only Linux/macOS

# From old release: 
> 1.2.0 legacy for byte*/byte** and char*/char** for only Windows
But latest version 1.3.0 - Removed byte*/byte** and char*/char** because I won't work for Windows 11 or greater than 11 because I am working on Ubuntu 25.04 Sorry for that, Windows-Hackers - because some hackers are fault to use my old account. That is why my account was updated - you can't try to hack my accout. :D.

That is reason why do I not use Windows because hackers always open my backdoor. That is why I gave up to use Windows. That is hard punishment against Windows!

Now I use only Linux. Sorry I will release soon Gtk4 ( 4.19.2 ), Cairo-1 ( 1.18 ) and Glib-2.0 ( 2.85.0 ) ( DeafMan1983.Interop.Gtk4 - It will come soon )
NOTE: It doesn't work for Msys2-GTk4 or latest version of Gtk 4 under Windows.

# Explanation about sbyte* and sbyte**

Example:
SDL3's Wrapper ( DeafMan1983.Interop.SDL3 - It will come soon )
```cs
sbyte* title = StringToSBytePointer("Hello SDL3");
SDL_Window* window = SDL_CreateWindow(title, ...);
```

Gtk4 ( 4.19.2 ) + Glib-2.0 ( 2.85.0 ) Simple Gtk4's application
```cs
// OnActivate(...)
GtkWidget* window = gtk_application_window(app);
gtk_window_set_title(GTK_WINDOW(window), StringToSBytePointer("Hello Gtk4"));
...
```
Gtk4 ( 4.19.2 ) + Glib-2.0 ( 2.85.0 ) via GType System ( without G_DEFINE_TYPE and G_DEFINE_FINAL_TYPE )
```cs
public static unsafe ExampleApp* example_app_new()
{
    return (ExampleApp*)g_object_new(EXAMPLE_APP_TYPE, StringToSBytePointer("application-id"), StringToSBytePointer("org.gtk.exampleapp"), StringToSBytePointer("flags"), GApplicationFlags.G_APPLICATION_HANDLES_OPEN, null);
}
```
or for sbyte**:
```cs
// static int Main() // without string[] args inside parameter of Main because Gtk4 went wrong... if y<ou work GType System.
string[] args = Environment.GetCommandLineArgs(); // FIX ME It is workking perfectly.
int argc = args.Length;
sbyte** argv = StringArrayToSByteDoublePointer(args);
return g_application_run(G_APPLICATION(example_app_new()), argc, argv);
```

Enjoy your development with C#!
