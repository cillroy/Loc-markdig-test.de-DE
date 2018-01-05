---
title: TITEL DES ARTIKELS | DIENSTNAME
description: 
keywords: 
author: GITHUB USERNAME
manager: ALIAS
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: GET ONE FROM guidgenerator.com
ms.openlocfilehash: 68090a038cec49009b6bd0ce0515a075f62483b8
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="0b44a-102">Metadaten- und Markdown-Vorlage</span><span class="sxs-lookup"><span data-stu-id="0b44a-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="0b44a-103">Diese docs.ms-Vorlage enthält Beispiele für Markdown-Syntax sowie Anleitungen zum Festlegen der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="0b44a-103">This docs.ms template contains examples of markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="0b44a-104">Sie steht im Stammverzeichnis jedes EM-Pilotrepositorys (z. B. „~/Azure-RMSDocs-pr /template.md“) zur Verfügung und soll als Markdown-Datei gelesen werden, obwohl Sie die [veröffentlichte Version](https://stage.docs.microsoft.com/en-us/rights-management/template) verwenden können, um festzustellen, wie die Markdown-Beispiele dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0b44a-104">It is available in the root directory of each EM Pilot repository (e.g. ~/Azure-RMSDocs-pr /template.md) and is meant to be read as a markdown file, although you can refer to [the published version](https://stage.docs.microsoft.com/en-us/rights-management/template) to see how the markdown examples rendeer.</span></span>

<span data-ttu-id="0b44a-105">Beim Erstellen einer Markdown-Datei sollten Sie die Vorlage in eine neue Datei kopieren, die Metadaten wie unten angegeben ausfüllen, die H1-Überschrift oben auf den Titel des Artikels festlegen und den Inhalt löschen.</span><span class="sxs-lookup"><span data-stu-id="0b44a-105">When creating a markdown file you shluld copy the template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span> 


## <a name="metadata"></a><span data-ttu-id="0b44a-106">Metadaten</span><span class="sxs-lookup"><span data-stu-id="0b44a-106">Metadata</span></span> 

<span data-ttu-id="0b44a-107">Den vollständigen Metadatenblock finden Sie oben, unterteilt in erforderliche Felder und optionale Felder. Weitere Informationen finden Sie auf dem [OPS-Metadatenmerkblatt](https://ppe.msdn.microsoft.com/en-us/ce-csi-docs/ops/ops-onboarding/managing-content/content-meta-data).</span><span class="sxs-lookup"><span data-stu-id="0b44a-107">The full metadata block is above, divided into required fields and optional fields; see the [OPS metadata cheatsheet](https://ppe.msdn.microsoft.com/en-us/ce-csi-docs/ops/ops-onboarding/managing-content/content-meta-data) for more details.</span></span> <span data-ttu-id="0b44a-108">Wichtige Hinweise:</span><span class="sxs-lookup"><span data-stu-id="0b44a-108">Some key notes:</span></span>

- <span data-ttu-id="0b44a-109">Sie **müssen** ein Leerzeichen zwischen dem Doppelpunkt (:) und dem Wert für ein Metadatenelement einfügen.</span><span class="sxs-lookup"><span data-stu-id="0b44a-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="0b44a-110">Wenn ein optionales Metadatenelement keinen Wert aufweist, kommentieren Sie das Element mit einem # (lassen Sie es nicht leer und verwenden Sie kein „na“). Wenn Sie einen Wert einem Element hinzufügen, das auskommentiert wurde, sollten Sie das # unbedingt löschen.</span><span class="sxs-lookup"><span data-stu-id="0b44a-110">If an optional metadata element does not have a value, comment out the element with a # (do not leave it blank or use "na"); if you are adding a value to an element that was commnted out, be sure to remove the #.</span></span>
- <span data-ttu-id="0b44a-111">Doppelpunkte in einem Wert (z. B. ein Titel) unterbrechen den Metadaten-Parser.</span><span class="sxs-lookup"><span data-stu-id="0b44a-111">Colons in a value (e.g., a title) break the metadata parser.</span></span> <span data-ttu-id="0b44a-112">Verwenden Sie stattdessen die HTML-Codierung „&#58;“ (z. B. „Titel: Azure Rights Management&#58; die Grundlagen | Azure RMS“).</span><span class="sxs-lookup"><span data-stu-id="0b44a-112">In their place, use the HTML encoding of &#58; (e.g., "title: Azure Rights Management&#58; the basics | Azure RMS").</span></span>
- <span data-ttu-id="0b44a-113">**Titel**: Dieser Titel wird in Suchergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b44a-113">**title**: This title will appear in search engine results.</span></span> <span data-ttu-id="0b44a-114">Der Titel sollte mit einem senkrechten Strich (|) gefolgt vom Namen des Diensts (z. B. siehe oben) enden.</span><span class="sxs-lookup"><span data-stu-id="0b44a-114">The title should end with a pipe (|) followed by the name of the service (e.g. see above).</span></span> <span data-ttu-id="0b44a-115">Der Titel muss nicht (und sollte nicht) mit dem Titel in der H1-Überschrift übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="0b44a-115">The title need not (and probably should not) be identical to the title in your H1 heading.</span></span> <span data-ttu-id="0b44a-116">Er sollte ungefähr 65 Zeichen (einschließlich | NAME DES DIENSTS) umfassen.</span><span class="sxs-lookup"><span data-stu-id="0b44a-116">It should be roughly 65 characters (including | SERVICE NAME)</span></span>
- <span data-ttu-id="0b44a-117">**Autor**, **Manager**, **Prüfer**: Das Autorenfeld sollte den **Github-Benutzernamen** des Autors enthalten, nicht den Alias.</span><span class="sxs-lookup"><span data-stu-id="0b44a-117">**author**, **manager**, **reviewer**: The author field should contain the **Github username** of the author, not their alias.</span></span>  <span data-ttu-id="0b44a-118">Die Felder „Manager“ und „Prüfer“ sollten andererseits Aliasnamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0b44a-118">The "manager" and "reviewer" fields, on the other hand, should contain aliases.</span></span> <span data-ttu-id="0b44a-119">„ms.reviewer“ gibt den Namen des Projektmanagers an, der dem Artikel oder Dienst zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0b44a-119">ms.reviewer specifies the name of the PM associated with the article or service.</span></span>
- <span data-ttu-id="0b44a-120">**ms.assetid**: Dies ist die GUID des Artikels in Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="0b44a-120">**ms.assetid**: This is the GUID of the article from CAPS.</span></span> <span data-ttu-id="0b44a-121">Wenn Sie eine neue Markdown-Datei erstellen, rufen Sie eine GUID von [https://www.guidgenerator.com](https://www.guidgenerator.com) ab.</span><span class="sxs-lookup"><span data-stu-id="0b44a-121">When creating a new markdown file, get a GUID from [https://www.guidgenerator.com](https://www.guidgenerator.com).</span></span> 
- <span data-ttu-id="0b44a-122">**ms.prod**, **ms.service**, **ms.technology**, **ms.devlang**, **ms.topic**, **ms.tgt_pltfrm**: Mögliche Werte für diese Elemente finden Sie [hier](https://microsoft.sharepoint.com/teams/STBCSI/Insights/_layouts/15/WopiFrame.aspx?sourcedoc=%7b7A321BF1-0611-4184-84DA-A0E964C435FA%7d&file=WEDCS_MasterList_CSIValues.xlsx&action=default).</span><span class="sxs-lookup"><span data-stu-id="0b44a-122">**ms.prod**, **ms.service**, **ms.technology**, **ms.devlang**, **ms.topic**, **ms.tgt_pltfrm**: Possible values for these elements can be found [here](https://microsoft.sharepoint.com/teams/STBCSI/Insights/_layouts/15/WopiFrame.aspx?sourcedoc=%7b7A321BF1-0611-4184-84DA-A0E964C435FA%7d&file=WEDCS_MasterList_CSIValues.xlsx&action=default).</span></span>

## <a name="basic-markdown-and-gfm"></a><span data-ttu-id="0b44a-123">Grundlegendes Markdown und GFM</span><span class="sxs-lookup"><span data-stu-id="0b44a-123">Basic Markdown and GFM</span></span>

<span data-ttu-id="0b44a-124">Alle grundlegenden und Github-flavored Markdowns werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0b44a-124">All basic and Github-flavored markdown is supported.</span></span> <span data-ttu-id="0b44a-125">Weitere Informationen dazu finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0b44a-125">For more information on these, see:</span></span>

- [<span data-ttu-id="0b44a-126">Baseline-Markdown-Syntax</span><span class="sxs-lookup"><span data-stu-id="0b44a-126">Baseline markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="0b44a-127">GFM-Dokumentation (Github-flavored Markdown)</span><span class="sxs-lookup"><span data-stu-id="0b44a-127">Github-flavored markdown (GFM) documentation</span></span>](https://guides.github.com/features/mastering-markdown)

## <a name="headings"></a><span data-ttu-id="0b44a-128">Überschriften</span><span class="sxs-lookup"><span data-stu-id="0b44a-128">Headings</span></span>

<span data-ttu-id="0b44a-129">Beispiele für Überschriften der ersten und zweiten Ebene finden Sie oben.</span><span class="sxs-lookup"><span data-stu-id="0b44a-129">Examples of first- and second-level headings are above.</span></span> 

<span data-ttu-id="0b44a-130">Im Thema **darf nur** eine Überschrift der ersten Ebene vorhanden sein, die als Titel auf der Seite angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0b44a-130">There **must** be only one first-level heading in your topic, which will be displayed as the on-page title.</span></span>  

<span data-ttu-id="0b44a-131">Überschriften der zweiten Ebene generiert das Inhaltsverzeichnis auf der Seite, die im Abschnitt „In diesem Artikel“ unter dem Seitentitel angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0b44a-131">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="0b44a-132">Überschrift der dritten Ebene</span><span class="sxs-lookup"><span data-stu-id="0b44a-132">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="0b44a-133">Überschrift der vierten Ebene</span><span class="sxs-lookup"><span data-stu-id="0b44a-133">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="0b44a-134">Überschrift der fünften Ebene</span><span class="sxs-lookup"><span data-stu-id="0b44a-134">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="0b44a-135">Überschrift der sechsten Ebene</span><span class="sxs-lookup"><span data-stu-id="0b44a-135">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="0b44a-136">Textformat</span><span class="sxs-lookup"><span data-stu-id="0b44a-136">Text styling</span></span>

<span data-ttu-id="0b44a-137">*Kursiv*</span><span class="sxs-lookup"><span data-stu-id="0b44a-137">*Italics*</span></span> 

<span data-ttu-id="0b44a-138">**Fett**</span><span class="sxs-lookup"><span data-stu-id="0b44a-138">**Bold**</span></span> 

<span data-ttu-id="0b44a-139">~~Durchgestrichen~~</span><span class="sxs-lookup"><span data-stu-id="0b44a-139">~~Strikethrough~~</span></span>



## <a name="links"></a><span data-ttu-id="0b44a-140">Links</span><span class="sxs-lookup"><span data-stu-id="0b44a-140">Links</span></span>

<span data-ttu-id="0b44a-141">Verwenden Sie für die Verknüpfung mit einer Markdown-Datei im gleichen Repository [relative Links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2).</span><span class="sxs-lookup"><span data-stu-id="0b44a-141">To link to a markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2).</span></span> 

- <span data-ttu-id="0b44a-142">Beispiel: [Was ist Azure Rights Management?](./understand-explore/what-is-azure-rights-management.md)</span><span class="sxs-lookup"><span data-stu-id="0b44a-142">Example: [What is Azure Rights Management](./understand-explore/what-is-azure-rights-management.md)</span></span>

<span data-ttu-id="0b44a-143">Um einen Header in der gleichen Markdown-Datei zu verknüpfen, zeigen Sie die Quelle des veröffentlichten Artikels an, suchen Sie nach der ID des Headers (z. B. `id="blockquote"`), und verknüpfen Sie mit # + ID (z. B. `#blockquote`).</span><span class="sxs-lookup"><span data-stu-id="0b44a-143">To link to a header in the same markdown file, view the source of the published article, find the id of the head (e.g. `id="blockquote"`, and link using # + id (e.g. `#blockquote`).</span></span>

- <span data-ttu-id="0b44a-144">Beispiel: [Blockquotes](#blockquote)</span><span class="sxs-lookup"><span data-stu-id="0b44a-144">Example: [Blockquotes](#blockquote)</span></span>

<span data-ttu-id="0b44a-145">Verwenden Sie für die Verknüpfung mit einem Header in einer Markdown-Datei im gleichen Repository relative Links und Hashtag-Links.</span><span class="sxs-lookup"><span data-stu-id="0b44a-145">To link to a header in a markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="0b44a-146">Beispiel: [technische Übersicht des Anmeldevorgangs](./understand-explore/rms-for-individuals-user-signup.md#technical-overview-of-the-sign-up-process)</span><span class="sxs-lookup"><span data-stu-id="0b44a-146">Example: [technical overiew of the sign-up process](./understand-explore/rms-for-individuals-user-signup.md#technical-overview-of-the-sign-up-process)</span></span>

<span data-ttu-id="0b44a-147">Um eine externe Datei zu verknüpfen, verwenden Sie den vollständigen URL als Link.</span><span class="sxs-lookup"><span data-stu-id="0b44a-147">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="0b44a-148">Beispiel: [Github](http://www.github.com)</span><span class="sxs-lookup"><span data-stu-id="0b44a-148">Example: [Github](http://www.github.com)</span></span>

<span data-ttu-id="0b44a-149">Wenn eine URL in einer Markdown-Datei angezeigt wird, wird sie in einen klickbaren Link umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="0b44a-149">If a URL appears in a markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="0b44a-150">Beispiel: http://www.github.com</span><span class="sxs-lookup"><span data-stu-id="0b44a-150">Example: http://www.github.com</span></span>

## <a name="lists"></a><span data-ttu-id="0b44a-151">Listen</span><span class="sxs-lookup"><span data-stu-id="0b44a-151">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="0b44a-152">Sortierte Listen</span><span class="sxs-lookup"><span data-stu-id="0b44a-152">Ordered lists</span></span>

1. <span data-ttu-id="0b44a-153">Dieses</span><span class="sxs-lookup"><span data-stu-id="0b44a-153">This</span></span> 
1. <span data-ttu-id="0b44a-154">Ist</span><span class="sxs-lookup"><span data-stu-id="0b44a-154">Is</span></span>
1. <span data-ttu-id="0b44a-155">Eine</span><span class="sxs-lookup"><span data-stu-id="0b44a-155">An</span></span>
1. <span data-ttu-id="0b44a-156">Sortierte</span><span class="sxs-lookup"><span data-stu-id="0b44a-156">Ordered</span></span>
1. <span data-ttu-id="0b44a-157">List</span><span class="sxs-lookup"><span data-stu-id="0b44a-157">List</span></span>  


#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="0b44a-158">Sortierte Liste mit einer eingebetteten Liste</span><span class="sxs-lookup"><span data-stu-id="0b44a-158">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="0b44a-159">Here</span><span class="sxs-lookup"><span data-stu-id="0b44a-159">Here</span></span>
1. <span data-ttu-id="0b44a-160">kommt</span><span class="sxs-lookup"><span data-stu-id="0b44a-160">comes</span></span>
1. <span data-ttu-id="0b44a-161">eine</span><span class="sxs-lookup"><span data-stu-id="0b44a-161">an</span></span>
1. <span data-ttu-id="0b44a-162">eingebettete</span><span class="sxs-lookup"><span data-stu-id="0b44a-162">embedded</span></span>
    1. <span data-ttu-id="0b44a-163">Miss Scarlett</span><span class="sxs-lookup"><span data-stu-id="0b44a-163">Miss Scarlett</span></span>
    1. <span data-ttu-id="0b44a-164">Professor Plum</span><span class="sxs-lookup"><span data-stu-id="0b44a-164">Professor Plum</span></span>
1. <span data-ttu-id="0b44a-165">sortierte</span><span class="sxs-lookup"><span data-stu-id="0b44a-165">ordered</span></span>
1. <span data-ttu-id="0b44a-166">list</span><span class="sxs-lookup"><span data-stu-id="0b44a-166">list</span></span>


### <a name="unordered-lists"></a><span data-ttu-id="0b44a-167">Unsortierte Listen</span><span class="sxs-lookup"><span data-stu-id="0b44a-167">Unordered Lists</span></span>

- <span data-ttu-id="0b44a-168">Dieses</span><span class="sxs-lookup"><span data-stu-id="0b44a-168">This</span></span>
- <span data-ttu-id="0b44a-169">ist</span><span class="sxs-lookup"><span data-stu-id="0b44a-169">is</span></span>
- <span data-ttu-id="0b44a-170">einer</span><span class="sxs-lookup"><span data-stu-id="0b44a-170">a</span></span>
- <span data-ttu-id="0b44a-171">Aufzählung</span><span class="sxs-lookup"><span data-stu-id="0b44a-171">bulleted</span></span>
- <span data-ttu-id="0b44a-172">list</span><span class="sxs-lookup"><span data-stu-id="0b44a-172">list</span></span>


##### <a name="unordered-list-with-an-embedded-lists"></a><span data-ttu-id="0b44a-173">Unsortierte Liste mit einer eingebetteten Liste</span><span class="sxs-lookup"><span data-stu-id="0b44a-173">Unordered list with an embedded lists</span></span>

- <span data-ttu-id="0b44a-174">Dieses</span><span class="sxs-lookup"><span data-stu-id="0b44a-174">This</span></span> 
- <span data-ttu-id="0b44a-175">Aufzählung</span><span class="sxs-lookup"><span data-stu-id="0b44a-175">bulleted</span></span> 
- <span data-ttu-id="0b44a-176">list</span><span class="sxs-lookup"><span data-stu-id="0b44a-176">list</span></span>
    - <span data-ttu-id="0b44a-177">Mrs. Peacock</span><span class="sxs-lookup"><span data-stu-id="0b44a-177">Mrs. Peacock</span></span>
    - <span data-ttu-id="0b44a-178">Mr. Green</span><span class="sxs-lookup"><span data-stu-id="0b44a-178">Mr. Green</span></span>
- <span data-ttu-id="0b44a-179">enthält</span><span class="sxs-lookup"><span data-stu-id="0b44a-179">contains</span></span>  
- <span data-ttu-id="0b44a-180">Andere</span><span class="sxs-lookup"><span data-stu-id="0b44a-180">other</span></span>
    1. <span data-ttu-id="0b44a-181">Colonel Mustard</span><span class="sxs-lookup"><span data-stu-id="0b44a-181">Colonel Mustard</span></span>
    1. <span data-ttu-id="0b44a-182">Mrs. White</span><span class="sxs-lookup"><span data-stu-id="0b44a-182">Mrs. White</span></span>
- <span data-ttu-id="0b44a-183">Listen</span><span class="sxs-lookup"><span data-stu-id="0b44a-183">lists</span></span>


## <a name="horizontal-rule"></a><span data-ttu-id="0b44a-184">Horizontale Regel</span><span class="sxs-lookup"><span data-stu-id="0b44a-184">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="0b44a-185">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0b44a-185">Tables</span></span>

| <span data-ttu-id="0b44a-186">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0b44a-186">Tables</span></span>        | <span data-ttu-id="0b44a-187">Sind</span><span class="sxs-lookup"><span data-stu-id="0b44a-187">Are</span></span>           | <span data-ttu-id="0b44a-188">Gut</span><span class="sxs-lookup"><span data-stu-id="0b44a-188">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="0b44a-189">Sp 3 ist</span><span class="sxs-lookup"><span data-stu-id="0b44a-189">col 3 is</span></span>      | <span data-ttu-id="0b44a-190">rechtsbündig</span><span class="sxs-lookup"><span data-stu-id="0b44a-190">right-aligned</span></span> | <span data-ttu-id="0b44a-191">$1600</span><span class="sxs-lookup"><span data-stu-id="0b44a-191">$1600</span></span> |
| <span data-ttu-id="0b44a-192">Sp 2 ist</span><span class="sxs-lookup"><span data-stu-id="0b44a-192">col 2 is</span></span>      | <span data-ttu-id="0b44a-193">zentriert</span><span class="sxs-lookup"><span data-stu-id="0b44a-193">centered</span></span>      |   <span data-ttu-id="0b44a-194">12 $</span><span class="sxs-lookup"><span data-stu-id="0b44a-194">$12</span></span> |
| <span data-ttu-id="0b44a-195">SP 1 ist der Standard</span><span class="sxs-lookup"><span data-stu-id="0b44a-195">col 1 is default</span></span> | <span data-ttu-id="0b44a-196">linksbündig</span><span class="sxs-lookup"><span data-stu-id="0b44a-196">left-aligned</span></span>     |    <span data-ttu-id="0b44a-197">$1</span><span class="sxs-lookup"><span data-stu-id="0b44a-197">$1</span></span> |


## <a name="code"></a><span data-ttu-id="0b44a-198">Code</span><span class="sxs-lookup"><span data-stu-id="0b44a-198">Code</span></span>

### <a name="codeblock"></a><span data-ttu-id="0b44a-199">Codeblock</span><span class="sxs-lookup"><span data-stu-id="0b44a-199">Codeblock</span></span>

    function fancyAlert(arg) {
      if(arg) {
        $.docs({div:'#foo'})
      }
    }

### <a name="in-line-code"></a><span data-ttu-id="0b44a-200">Inlinecode</span><span class="sxs-lookup"><span data-stu-id="0b44a-200">In-line code</span></span>

<span data-ttu-id="0b44a-201">Dies ist ein Beispiel für `in-line code`.</span><span class="sxs-lookup"><span data-stu-id="0b44a-201">This is an example of `in-line code`.</span></span>

## <a name="blockquotes"></a><span data-ttu-id="0b44a-202">Blockquotes</span><span class="sxs-lookup"><span data-stu-id="0b44a-202">Blockquotes</span></span>

> <span data-ttu-id="0b44a-203">Die Trockenheit hatte nun zehn Millionen Jahre lang angehalten, und die Herrschaft der schrecklichen Echsen hatte längst geendet.</span><span class="sxs-lookup"><span data-stu-id="0b44a-203">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="0b44a-204">Hier am Äquator, in dem Kontinent, der eines Tages zu Afrika werden würde, hatte der Kampf ums Überleben eine neue Wildheit erreicht, und ein Sieger war noch nicht in Sicht.</span><span class="sxs-lookup"><span data-stu-id="0b44a-204">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="0b44a-205">In diesem trostlosen und verdorrten Land konnte nur der Kleine, der Schnelle oder der Wilde gedeihen oder zumindest überleben.</span><span class="sxs-lookup"><span data-stu-id="0b44a-205">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="0b44a-206">Bilder</span><span class="sxs-lookup"><span data-stu-id="0b44a-206">Images</span></span>

### <a name="static-image"></a><span data-ttu-id="0b44a-207">Statisches Bild</span><span class="sxs-lookup"><span data-stu-id="0b44a-207">Static Image</span></span>

![dies ist der alternative Text](./media/AzRMS_elements.png)

### <a name="linked-image"></a><span data-ttu-id="0b44a-209">Verknüpftes Bild</span><span class="sxs-lookup"><span data-stu-id="0b44a-209">Linked Image</span></span>

<span data-ttu-id="0b44a-210">[![alternativer Text für verknüpftes Bild](./media/AzRMS_elements.png)](https://azure.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0b44a-210">[![alt text for linked image](./media/AzRMS_elements.png)](https://azure.microsoft.com)</span></span> 

### <a name="animated-gif"></a><span data-ttu-id="0b44a-211">Animiertes GIF</span><span class="sxs-lookup"><span data-stu-id="0b44a-211">Animated gif</span></span>

![Animiertes GIF](./media/hololens.gif)

## <a name="alerts"></a><span data-ttu-id="0b44a-213">Warnungen</span><span class="sxs-lookup"><span data-stu-id="0b44a-213">Alerts</span></span>

### <a name="note"></a><span data-ttu-id="0b44a-214">Hinweis</span><span class="sxs-lookup"><span data-stu-id="0b44a-214">Note</span></span>

> [!NOTE]
> <span data-ttu-id="0b44a-215">Dies ist ein HINWEIS</span><span class="sxs-lookup"><span data-stu-id="0b44a-215">This is NOTE</span></span>

### <a name="warning"></a><span data-ttu-id="0b44a-216">Warning</span><span class="sxs-lookup"><span data-stu-id="0b44a-216">Warning</span></span>

> [!WARNING]
> <span data-ttu-id="0b44a-217">Dies ist eine WARNUNG</span><span class="sxs-lookup"><span data-stu-id="0b44a-217">This is WARNING</span></span>

### <a name="tip"></a><span data-ttu-id="0b44a-218">Tipp</span><span class="sxs-lookup"><span data-stu-id="0b44a-218">Tip</span></span>

> [!TIP]
> <span data-ttu-id="0b44a-219">Dies ist ein TIPP</span><span class="sxs-lookup"><span data-stu-id="0b44a-219">This is TIP</span></span>

### <a name="important"></a><span data-ttu-id="0b44a-220">Wichtig</span><span class="sxs-lookup"><span data-stu-id="0b44a-220">Important</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b44a-221">Dies ist WICHTIG</span><span class="sxs-lookup"><span data-stu-id="0b44a-221">This is IMPORTANT</span></span>

## <a name="videos"></a><span data-ttu-id="0b44a-222">Videos</span><span class="sxs-lookup"><span data-stu-id="0b44a-222">Videos</span></span>

### <a name="channel-9"></a><span data-ttu-id="0b44a-223">Channel 9</span><span class="sxs-lookup"><span data-stu-id="0b44a-223">Channel 9</span></span>

<iframe src="http://channel9.msdn.com/Series/Azure-Active-Directory-Videos-Demos/Azure-Active-Directory-Connect-Express-Settings/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>


### <a name="youtube"></a><span data-ttu-id="0b44a-224">YouTube</span><span class="sxs-lookup"><span data-stu-id="0b44a-224">Youtube</span></span>

<iframe width="420" height="315" src="https://www.youtube.com/embed/R6_eWWfNB54" frameborder="0" allowfullscreen></iframe>

## <a name="docsms-extentions"></a><span data-ttu-id="0b44a-225">docs.ms-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="0b44a-225">docs.ms extentions</span></span>

### <a name="button"></a><span data-ttu-id="0b44a-226">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0b44a-226">Button</span></span>

> [!div class="button"]
[<span data-ttu-id="0b44a-227">Schaltflächenlinks</span><span class="sxs-lookup"><span data-stu-id="0b44a-227">button links</span></span>](/rights-management)

### <a name="selector"></a><span data-ttu-id="0b44a-228">Selector</span><span class="sxs-lookup"><span data-stu-id="0b44a-228">Selector</span></span>

> [!div class="op_single_selector"]
- [<span data-ttu-id="0b44a-229">foo</span><span class="sxs-lookup"><span data-stu-id="0b44a-229">foo</span></span>](/rights-management/template.md)
- [<span data-ttu-id="0b44a-230">bar</span><span class="sxs-lookup"><span data-stu-id="0b44a-230">bar</span></span>](/rights-management/scratch.md)

### <a name="step-by-step"></a><span data-ttu-id="0b44a-231">Schrittweise</span><span class="sxs-lookup"><span data-stu-id="0b44a-231">Step-By-Step</span></span>

>[!div class="step-by-step"]
[Zurück](https://www.example.com)
[Weiter](https://www.example.com)