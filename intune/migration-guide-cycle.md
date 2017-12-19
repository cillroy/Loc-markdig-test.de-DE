---
title: Funktionsweise eines typischen Migrationszyklus in Intune
description: "In diesem Artikel wird erläutert, wie ein Intune-Migrationszyklus funktioniert. Zudem enthält er Beispiele für den Umgang mit den Migrationszyklen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 34e748e16449a99bad4c1f3e96c22dda6d8f3018
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2017
---
# <a name="typical-migration-cycle"></a>Typischer Migrationszyklus

Es ist üblich, dass eine Organisation ihre Intune-Migration mit einem kleinen Pilotversuch mit einer Teilmenge aller Benutzer in ihrer IT-Abteilung startet. Zusätzlich muss Ihre Organisation möglicherweise Faktoren wie die Änderungsbereitschaft der Gruppe, die Anzahl der Benutzer, die Komplexität, die Anforderungen, den Ort und die Geschäftsrisiken besprechen, um einen Zeitrahmen für die Migration festlegen zu können.

Hier ist ein Beispiel, wie Sie Ihre Zielgruppen planen können:

  | **Migration der Zielgruppen** | **Zeitraum 1** | **Zeitraum 2** | **Zeitraum 3** | **Zeitraum 4** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Begrenzter Pilotversuch der IT-Organisation (50 Benutzer) | Plan bekannt geben | Anweisung zum Registrieren | Frist setzen | Erzwingen des bedingten Zugriffs |  |                                                        
| Erweiterter Pilotversuch der IT-Organisation (200 Benutzer) |  | Plan bekannt geben | Anweisung zum Registrieren | Frist setzen | Erzwingen des bedingten Zugriffs |
| Phase 1 der Migration Technologisch kompetente Benutzer (2000) |  |  | Plan bekannt geben | Anweisung zum Registrieren | Frist setzen |
| Phase 2 der Migration Osten der USA |  |  |  | Plan bekannt geben | Anweisung zum Registrieren |
| Alle Regionen |  |  |  |  | Plan bekannt geben |

## <a name="customer-migration-case-study"></a>Fallstudie für die Kundenmigration

### <a name="adatum-corporation"></a>Adatum Corporation

Schauen Sie sich an, [wie Adatum Corporation von einer Drittanbieter-MDM zu Intune migriert ist](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Migrationsüberwachung

Intune stellt mehrere Methoden bereit, mit denen Sie Ihre Migration überwachen können:

* Gruppenansichten für Intune-Benutzer

* Integrierte Berichte

* Konsoleninterne Warnungen

Verfolgen Sie nach, wie viele Benutzer nach jeder Phase Geräte registriert haben, damit Sie:

-   die Effektivität der Kommunikationsplan bewerten können

-   die Auswirkungen des Erzwingens von bedingtem Zugriff einschätzen können


## <a name="post-migration"></a>Aufgaben nach der Migration

Setzen Sie den vorherigen MDM-Anbieter außer Kraft, und beenden Sie das Abonnement des Diensts, nachdem Sie zu Intune migriert sind. Darüber hinaus müssen Sie alle nicht benötigten Infrastrukturanforderungen entfernen, indem Sie den Anweisungen des MDM-Anbieters folgen.
