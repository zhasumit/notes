

All the data types with modifiers to make their range compensate as per the values

|Type Declaration|Size (Bytes)*|Value Range (Typical)**|Description|
|---|---|---|---|
|`bool`|1|`true` or `false`|Boolean type|
|`char`|1|-128 to 127|Character (signed by default, implementation-defined)|
|`signed char`|1|-128 to 127|Explicitly signed char|
|`unsigned char`|1|0 to 255|Unsigned char|
|`wchar_t`|2 or 4|0 to 65,535 (2 bytes) or 0 to 4,294,967,295 (4 bytes)|Wide character|
|`char8_t` (C++20)|1|0 to 255|UTF-8 character|
|`char16_t` (C++11)|2|0 to 65,535|UTF-16 character|
|`char32_t` (C++11)|4|0 to 4,294,967,295|UTF-32 character|
|`short` / `short int`|2|-32,768 to 32,767|Short integer|
|`signed short` / `signed short int`|2|-32,768 to 32,767|Explicitly signed short|
|`unsigned short` / `unsigned short int`|2|0 to 65,535|Unsigned short|
|`int`|4|-2,147,483,648 to 2,147,483,647|Integer|
|`signed int`|4|-2,147,483,648 to 2,147,483,647|Explicitly signed int|
|`unsigned int`|4|0 to 4,294,967,295|Unsigned int|
|`long` / `long int`|4 or 8|-2,147,483,648 to 2,147,483,647 (4 bytes)|Long integer|
|`signed long` / `signed long int`|4 or 8|-2,147,483,648 to 2,147,483,647 (4 bytes)|Explicitly signed long|
|`unsigned long` / `unsigned long int`|4 or 8|0 to 4,294,967,295 (4 bytes)|Unsigned long|
|`long long` / `long long int`|8|-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807|Long long integer|
|`signed long long` / `signed long long int`|8|-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807|Explicitly signed long long|
|`unsigned long long` / `unsigned long long int`|8|0 to 18,446,744,073,709,551,615|Unsigned long long|
|`float`|4|±3.4 × 10^38 (7 digits precision)|Single-precision floating point|
|`double`|8|±1.7 × 10^308 (15 digits precision)|Double-precision floating point|
|`long double`|12/16|±1.2 × 10^4932 (19 digits precision, implementation-defined)|Extended-precision floating point|
|`void`|0|n/a|Represents absence of value|
|`enum`|varies|Implementation-defined|User-defined enumeration|