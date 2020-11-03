---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-culture?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Culture
ms.openlocfilehash: d7e9ebd56db3ad9de2bfbcec62f73f1f8c0e2eaa
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200819"
---
# <span data-ttu-id="14303-103">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="14303-103">Get-Culture</span></span>

## <span data-ttu-id="14303-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="14303-104">SYNOPSIS</span></span>
<span data-ttu-id="14303-105">Ruft die aktuelle im Betriebssystem festgelegte Kultur ab.</span><span class="sxs-lookup"><span data-stu-id="14303-105">Gets the current culture set in the operating system.</span></span>

## <span data-ttu-id="14303-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14303-106">SYNTAX</span></span>

```
Get-Culture [<CommonParameters>]
```

## <span data-ttu-id="14303-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14303-107">DESCRIPTION</span></span>
<span data-ttu-id="14303-108">Mit dem " **Get-Culture"-** Cmdlet werden Informationen zu den aktuellen Kultur Einstellungen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="14303-108">The **Get-Culture** cmdlet gets information about the current culture settings.</span></span>
<span data-ttu-id="14303-109">Hierzu gehören Informationen über die aktuellen Spracheinstellungen des Systems, z. B. das Tastaturlayout und das Anzeigeformat für Elemente wie Zahlen, Währung und Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="14303-109">This includes information about the current language settings on the system, such as the keyboard layout, and the display format of items such as numbers, currency, and dates.</span></span>

<span data-ttu-id="14303-110">Sie können auch das Cmdlet "Get-UICulture" verwenden, das die aktuelle Benutzeroberflächen Kultur auf dem System abruft, und das Cmdlet " [Set-Culture](https://go.microsoft.com/fwlink/?LinkID=242258) " im internationalen Modul.</span><span class="sxs-lookup"><span data-stu-id="14303-110">You can also use the Get-UICulture cmdlet, which gets the current user interface culture on the system, and the [Set-Culture](https://go.microsoft.com/fwlink/?LinkID=242258) cmdlet in the International module.</span></span>
<span data-ttu-id="14303-111">Die Benutzeroberflächenkultur bestimmt, welche Textzeichenfolgen für die Elemente der Benutzeroberfläche, z. B. Menüs und Meldungen, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14303-111">The user-interface (UI) culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

## <span data-ttu-id="14303-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="14303-112">EXAMPLES</span></span>

### <span data-ttu-id="14303-113">Beispiel 1: Kultur Einstellungen erhalten</span><span class="sxs-lookup"><span data-stu-id="14303-113">Example 1: Get culture settings</span></span>

```
PS C:\> Get-Culture
```

<span data-ttu-id="14303-114">Dieser Befehl zeigt Informationen zu den regionalen Einstellungen auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="14303-114">This command displays information about the regional settings on the computer.</span></span>

### <span data-ttu-id="14303-115">Beispiel 2: Formatieren der Eigenschaften eines Culture-Objekts</span><span class="sxs-lookup"><span data-stu-id="14303-115">Example 2: Format the properties of a culture object</span></span>

```
PS C:\> $C = Get-Culture
PS C:\> $C | Format-List -Property *
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - 1033
TextInfo                       : TextInfo - 1033
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar, System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False PS C:\> $C.Calendar
MinSupportedDateTime : 1/1/0001 12:00:00 AM
MaxSupportedDateTime : 12/31/9999 11:59:59 PM
AlgorithmType        : SolarCalendar
CalendarType         : Localized
Eras                 : {1}
TwoDigitYearMax      : 2029
IsReadOnly           : False PS C:\> $C.DateTimeFormat
AMDesignator                     : AM
Calendar                         : System.Globalization.GregorianCalendar
DateSeparator                    : /
FirstDayOfWeek                   : Sunday
CalendarWeekRule                 : FirstDay
FullDateTimePattern              : dddd, MMMM dd, yyyy h:mm:ss tt
LongDatePattern                  : dddd, MMMM dd, yyyy
LongTimePattern                  : h:mm:ss tt
MonthDayPattern                  : MMMM dd
PMDesignator                     : PM
RFC1123Pattern                   : ddd, dd MMM yyyy HH':'mm':'ss 'GMT'
ShortDatePattern                 : M/d/yyyy
ShortTimePattern                 : h:mm tt
SortableDateTimePattern          : yyyy'-'MM'-'dd'T'HH':'mm':'ss
TimeSeparator                    : :
UniversalSortableDateTimePattern : yyyy'-'MM'-'dd HH':'mm':'ss'Z'
YearMonthPattern                 : MMMM, yyyy
AbbreviatedDayNames              : {Sun, Mon, Tue, Wed...}
ShortestDayNames                 : {Su, Mo, Tu, We...}
DayNames                         : {Sunday, Monday, Tuesday, Wednesday...}
AbbreviatedMonthNames            : {Jan, Feb, Mar, Apr...}
MonthNames                       : {January, February, March, April...}
IsReadOnly                       : False
NativeCalendarName               : Gregorian Calendar
AbbreviatedMonthGenitiveNames    : {Jan, Feb, Mar, Apr...}
MonthGenitiveNames               : {January, February, March, April...} PS C:\> $C.DateTimeFormat.FirstDayOfWeek
Sunday
```

<span data-ttu-id="14303-116">Dieses Beispiel zeigt die riesige Menge von Daten im Kulturobjekt.</span><span class="sxs-lookup"><span data-stu-id="14303-116">This example demonstrates the vast amount of data in the culture object.</span></span>
<span data-ttu-id="14303-117">Es zeigt, wie Sie die Eigenschaften und die untergeordneten Eigenschaften des Objekts anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="14303-117">It shows how to display the properties and sub-properties of the object.</span></span>

<span data-ttu-id="14303-118">Der erste Befehl verwendet das Cmdlet " **Get-Culture** ", um die aktuellen Kultur Einstellungen auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="14303-118">The first command uses the **Get-Culture** cmdlet to get the current culture settings on the computer.</span></span>
<span data-ttu-id="14303-119">Das resultierende Culture-Objekt wird in der $C-Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="14303-119">It stores the resulting culture object in the $C variable.</span></span>

<span data-ttu-id="14303-120">Der zweite Befehl zeigt alle Eigenschaften des Kulturobjekts an.</span><span class="sxs-lookup"><span data-stu-id="14303-120">The second command displays all of the properties of the culture object.</span></span>
<span data-ttu-id="14303-121">Er verwendet einen Pipeline Operator (|), um das Culture-Objekt in $C an das Format-List-Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="14303-121">It uses a pipeline operator (|) to send the culture object in $C to the Format-List cmdlet.</span></span>
<span data-ttu-id="14303-122">Er verwendet den *Property* -Parameter, um alle (\*) Eigenschaften des Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14303-122">It uses the *Property* parameter to display all (\*) properties of the object.</span></span>
<span data-ttu-id="14303-123">Dieser Befehl kann als abgekürzt werden `$c | fl *` .</span><span class="sxs-lookup"><span data-stu-id="14303-123">This command can be abbreviated as `$c | fl *`.</span></span>

<span data-ttu-id="14303-124">Die restlichen Befehle untersuchen die Eigenschaften des Kulturobjekts mithilfe der punktierten Schreibweise, um die Werte der Objekteigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14303-124">The remaining commands explore the properties of the culture object by using dot notation to display the values of the object properties.</span></span>
<span data-ttu-id="14303-125">Sie können diese Schreibweise verwenden, um den Wert einer beliebigen Eigenschaft des Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14303-125">You can use this notation to display the value of any property of the object.</span></span>

<span data-ttu-id="14303-126">Der dritte Befehl verwendet die punktierte Schreibweise, um den Wert der Calendar-Eigenschaft des Kulturobjekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14303-126">The third command uses dot notation to display the value of the Calendar property of the culture object.</span></span>

<span data-ttu-id="14303-127">Der vierte Befehl verwendet die punktierte Schreibweise, um den Wert der DateTimeFormat-Eigenschaft des Kulturobjekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14303-127">The fourth command uses dot notation to display the value of the DataTimeFormat property of the culture object.</span></span>

<span data-ttu-id="14303-128">Viele Objekteigenschaften verfügen wiederum über Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="14303-128">Many object properties have properties.</span></span>
<span data-ttu-id="14303-129">Der fünfte Befehl verwendet die punktierte Schreibweise, um den Wert der FirstDayOfWeek-Eigenschaft der DateTimeFormat-Eigenschaft anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14303-129">The fifth command uses dot notation to display the value of the FirstDayOfWeek property of the DateTimeFormat property.</span></span>

## <span data-ttu-id="14303-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14303-130">PARAMETERS</span></span>

### <span data-ttu-id="14303-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="14303-131">CommonParameters</span></span>
<span data-ttu-id="14303-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="14303-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14303-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="14303-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="14303-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="14303-134">INPUTS</span></span>

### <span data-ttu-id="14303-135">Keine</span><span class="sxs-lookup"><span data-stu-id="14303-135">None</span></span>
<span data-ttu-id="14303-136">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="14303-136">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="14303-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="14303-137">OUTPUTS</span></span>

### <span data-ttu-id="14303-138">System. Globalization. CultureInfo</span><span class="sxs-lookup"><span data-stu-id="14303-138">System.Globalization.CultureInfo</span></span>
<span data-ttu-id="14303-139">**Get-Culture** gibt ein Objekt zurück, das die aktuelle Kultur darstellt.</span><span class="sxs-lookup"><span data-stu-id="14303-139">**Get-Culture** returns an object that represents the current culture.</span></span>

## <span data-ttu-id="14303-140">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="14303-140">NOTES</span></span>

* <span data-ttu-id="14303-141">Sie können auch die Variablen „$PsCulture“ und „$PsUICulture“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="14303-141">You can also use the $PsCulture and $PsUICulture variables.</span></span> <span data-ttu-id="14303-142">Die $PsCulture-Variable speichert den Namen der aktuellen Kultur, und die $PsUICulture-Variable speichert den Namen der aktuellen Benutzeroberflächenkultur.</span><span class="sxs-lookup"><span data-stu-id="14303-142">The $PsCulture variable stores the name of the current culture and the $PsUICulture variable stores the name of the current UI culture.</span></span>

*

## <span data-ttu-id="14303-143">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="14303-143">RELATED LINKS</span></span>

[<span data-ttu-id="14303-144">Set-Culture</span><span class="sxs-lookup"><span data-stu-id="14303-144">Set-Culture</span></span>](/powershell/module/internationalcmdlets/set-culture)

[<span data-ttu-id="14303-145">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="14303-145">Get-UICulture</span></span>](Get-UICulture.md)