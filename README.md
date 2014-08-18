# Sitecore Profiling Module
Use this module to include profiling into your projects or modules. This module contains two separate projects and NuGet packages:

- `Unic.Profiling`: This is used for creating the profiling, add and stop profiling etc. in your code. This does actually nothing than firing some events.
- `Unic.Profiling.MiniProfiler`: This takes the profiling events from the other project and forward them to the MiniProfiler. Use this project if you want to see an output of the profiling settings from the other project.

## Installation
### Configuring profiling
Install the NuGet package `Unic.Profiling` on projects where you want to add a profiling.

### See profiling output
Install the NuGet package `Unic.Profiling.MiniProfiler` on web projects where you want to see the output of the configured profilings. After the installation you need to add the output directly before the closing `</body>` tag the view:

    @using StackExchange.Profiling;
    <head>
		...
    </head>
    <body>
		...
		@MiniProfiler.RenderIncludes()
    </body>

To disable the MiniProfiler output, you can set the following config in the `web.config` file. By default, MiniProfiler is enabled.

    <configuration>
    	<appSettings>
    		<add key="Profiling.DisableMiniProfier" value="true" />
    	</appSettings>
    </configuration>
	