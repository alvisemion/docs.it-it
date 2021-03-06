### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>Alcune API .NET causano eccezioni EntryPointNotFoundException first-chance gestite

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5, un numero limitato di metodi .NET ha iniziato a generare eccezioni <xref:System.EntryPointNotFoundException?displayProperty=name> first-chance. Queste eccezioni sono gestite all'interno di .NET Framework, ma possono interrompere l'automazione dei test che non si aspettano eccezioni first-chance. Queste stesse API causano errori in alcuni scenari di ApiVerifier con HighVersionLie abilitato.|
|Suggerimento|È possibile evitare questo bug eseguendo l'aggiornamento a .NET Framework 4.5.1. In alternativa, è possibile aggiornare l'automazione dei test in modo che non si interrompa in corrispondenza della prima <xref:System.EntryPointNotFoundException?displayProperty=name> first-chance.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)?displayProperty=nameWithType></li></ul>|

