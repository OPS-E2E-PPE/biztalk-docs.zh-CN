---
title: 导入 BizTalk 应用程序、 绑定和策略 |Microsoft Docs
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
ms.openlocfilehash: 7891d36e922f49efd8a5ce4f8986fcad8aa162aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382510"
---
# <a name="importing-biztalk-applications-bindings-and-policies"></a>导入 BizTalk 应用程序、 绑定和策略
在本部分中的主题介绍如何将 BizTalk 应用程序、 绑定和策略导入 BizTalk 组或应用程序。 如中所述[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)，导出应用程序创建 Windows Installer (.msi) 文件，您可以使用它将应用程序的项目导入其他 BizTalk 组中的应用程序。 如果组中不存在指定为导入的应用程序，创建应用程序。 此外，注册应用程序的项目，并且其数据存储在组的 BizTalk 数据库。 有关详细信息，请参阅[什么发生时导入项目](../core/what-happens-when-artifacts-are-imported.md)。  
  
 您还可以导入到 BizTalk 组或应用程序从 BizTalk 组、 应用程序或程序集，导出的绑定中所述[导出绑定](../core/exporting-bindings6.md)。 当您导入绑定时，它们将覆盖中 BizTalk 组、 应用程序或程序集具有相同名称的任何绑定。  
  
 此外，您可以将策略导入 BizTalk 组或应用程序中，从导出的 BizTalk 组中所述[如何导出策略](../core/how-to-export-a-policy.md)。 在新组中的应用程序然后可以使用该策略。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)  
  
-   [导入绑定](../core/importing-bindings2.md)  
  
-   [如何导入策略](../core/how-to-import-a-policy.md)