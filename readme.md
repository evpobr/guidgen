GUIDgen - alternative GUID generator GUI.
==============================================

Author: Akimov Vitaly.
License: LGPL 2.1.

Screenshots
-----------------

* Default window state:<br/>
![Default window](https://github.com/duox/guidgen/blob/master/docs/images/screenshot01.png)

* List of available GUID generators:<br/>
![GUID generators](https://github.com/duox/guidgen/blob/master/docs/images/screenshot02.png)

* List of available GUID formats:<br/>
![GUID formats](https://github.com/duox/guidgen/blob/master/docs/images/screenshot03.png)

* Internal help:<br/>
![Help window](https://github.com/duox/guidgen/blob/master/docs/images/screenshot04.png)

GUID generators
-----------------

A GUID generator creates a GUID which is sent to the selected formatter.

List of supported GUID generators:
- random GUID (implemented via CoCreateGuid),
- null GUID (all bytes are zero),
- invalid GUID (all bytes are 0xFF's),
- manual GUID (allows to manually give a GUID in the standard registry format and reformat it using one of formatters).

GUID formatters
-----------------

A GUID formatter takes GUID structure and makes a string in some format.

List of currently supported formatters:
- User-specified format

  User specifies the format in the "User format string" edit control and "Generate & Copy" button creates a formatted GUID.


- IMPLEMENT_OLECREATE

Example:
```cpp
// {BA4E6BB2-8A8B-4E81-B885-A6E1A9738574}
IMPLEMENT_OLECREATE( Class, Name, 0xba4e6bb2, 0x8a8b, 0x4e81, 0xb8, 0x85, 0xa6, 0xe1, 0xa9, 0x73, 0x85, 0x74 );
```


- DEFINE_GUID

Example:
```cpp
// {BA4E6BB2-8A8B-4E81-B885-A6E1A9738574}
DEFINE_GUID( Name, 0xba4e6bb2, 0x8a8b, 0x4e81, 0xb8, 0x85, 0xa6, 0xe1, 0xa9, 0x73, 0x85, 0x74 );
```


- static const struct GUID

Example:
```cpp
// {BA4E6BB2-8A8B-4E81-B885-A6E1A9738574}
static const struct GUID Name = { 0xba4e6bb2, 0x8a8b, 0x4e81, { 0xb8, 0x85, 0xa6, 0xe1, 0xa9, 0x73, 0x85, 0x74 } };
```


- standard registry format

Example:
{BA4E6BB2-8A8B-4E81-B885-A6E1A9738574}


- `[`Guid(" ... ")`]`

Example:
```cpp
[Guid("BA4E6BB2-8A8B-4E81-B885-A6E1A9738574")]
```


- `<`Guid(" ... ")`>`

Example:
```cpp
<Guid("BA4E6BB2-8A8B-4E81-B885-A6E1A9738574")>
```


- guid( ... )

Example:
```cpp
guid(BA4E6BB2-8A8B-4E81-B885-A6E1A9738574)
```


- `C#` field definition

Used to specify GUID fields in the `C#` field format.

Example:
```cpp
// {BA4E6BB2-8A8B-4E81-B885-A6E1A9738574}
static readonly Guid Name = new Guid(0xba4e6bb2, 0x8a8b, 0x4e81, 0xb8, 0x85, 0xa6, 0xe1, 0xa9, 0x73, 0x85, 0x74);
```

- VB .Net field definition

Example:
```vbnet
' {BA4E6BB2-8A8B-4E81-B885-A6E1A9738574}
Shared ReadOnly Name As Guid = New Guid(&Hba4e6bb2, &H8a8b, &H4e81, &Hb8, &H85, &Ha6, &He1, &Ha9, &H73, &H85, &H74)
```
