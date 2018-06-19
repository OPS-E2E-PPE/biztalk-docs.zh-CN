---
title: 导入 BizTalk 应用程序、 绑定和策略 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing, applications
- importing, policies
- applications, importing
- policies, importing
- importing, bindings
- bindings, importing
ms.assetid: 678bdb03-efaa-4053-9048-b71fc539d191
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18f7ea348fb34f4f8cc08e748799dcf8368a3c35
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256773"
---
# <a name="importing-biztalk-applications-bindings-and-policies"></a>导入 BizTalk 应用程序、 绑定和策略
本部分中的主题介绍如何将 BizTalk 应用程序、绑定和策略导入到 BizTalk 组或应用程序。 中所述[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)，导出应用程序创建 Windows Installer (.msi) 文件，然后，可以使用，以将应用程序的项目导入到不同的 BizTalk 组中的应用程序。 如果为导入指定的应用程序在组中不存在，则创建该应用程序。 此外，注册应用程序的项目，并将其数据存储于该组的 BizTalk Server 数据库中。 有关详细信息，请参阅[什么发生时项目导入](../core/what-happens-when-artifacts-are-imported.md)。  
  
 你还可以导入到 BizTalk 组或应用程序从 BizTalk 组、 应用程序或程序集，导出的绑定中所述[导出绑定](../core/exporting-bindings6.md)。 导入绑定时，它们将覆盖 BizTalk 组、应用程序或程序集中任何同名的绑定。  
  
 此外，你可以导入策略到 BizTalk 组或应用程序，从导出的 BizTalk 组中所述[如何导出策略](../core/how-to-export-a-policy.md)。 然后，新组中的应用程序可以使用该策略。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)  
  
-   [导入绑定](../core/importing-bindings2.md)  
  
-   [如何导入策略](../core/how-to-import-a-policy.md)