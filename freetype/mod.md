 * Download [FreeType 2.5.5](http://download.savannah.gnu.org/releases/freetype/freetype-2.5.5.tar.bz2)
 * Extract to `C:\mozilla-build\hexchat`
 * Copy `builds\windows\vc2010` to `builds\windows\vc2013`
 * In `builds\windows\vc2013\freetype.vcxproj`:
	* Replace `<PlatformToolset>v100</PlatformToolset>` with `<PlatformToolset>v120</PlatformToolset>`
	* Replace all `vc2010` in `<OutDir>` and `<IntDir>` with `vc2013`
	* Replace
`
    <TargetName Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">freetype255</TargetName>
    <TargetName Condition="'$(Configuration)|$(Platform)'=='Release|x64'">freetype255</TargetName>
` with
`
    <TargetName Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">freetype</TargetName>
    <TargetName Condition="'$(Configuration)|$(Platform)'=='Release|x64'">freetype</TargetName>
`
	* Add `<ClCompile Include="..\..\..\src\base\ftbdf.c" />`
	* Add `<Import Project="..\..\..\..\stack.props" />` at the end
	* Delete `<Optimization>` lines
