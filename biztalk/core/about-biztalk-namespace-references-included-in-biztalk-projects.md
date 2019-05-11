---
title: 有关 BizTalk 项目中包含的 BizTalk Namespace 引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- System.Xml namespace
- Microsoft.BizTalk.GlobalPropertySchemas namespace
- namespaces, System.Xml namespace
- System namespace
- namespaces, System namespace
- namespaces, Microsoft.BizTalk.GlobalPropertySchemas namespace
- Microsoft.BizTalk.DefaultPipelines namespace
- projects, namespaces
- namespaces, warnings
- namespaces, Microsoft.BIzTalk.DefaultPipelines namespace
- namespaces
ms.assetid: cb642eac-7307-44f8-bbba-3ae364e11ea2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01344253a75033650b0e6326ff11420d0ed6fef5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362404"
---
# <a name="about-biztalk-namespace-references-included-in-biztalk-projects"></a>有关 BizTalk 项目中包含的 BizTalk Namespace 引用
当添加新的 BizTalk 项目时，默认情况下包括以下命名空间：  
  
- **Microsoft.BizTalk.DefaultPipelines**  
  
- **Microsoft.BizTalk.GlobalPropertySchemas**  
  
- **系统**  
  
- **System.Xml**  
  
  此外可以添加新的引用和对你的项目的 Web 引用。 有关添加详细信息引用使用**项目**菜单中，请参阅[使用 Visual Studio](../core/using-visual-studio.md)。 有关添加 Web 引用的信息，请参阅[添加 Web 引用](../core/adding-web-references.md)。  
  
> [!CAUTION]
>  不要删除默认引用。 如果删除默认引用，你的项目中引用 BizTalk 项时可能遇到问题。 可以还原在解决方案资源管理器中的默认引用。  
  
> [!CAUTION]
>  如果你的 BizTalk 项目引用另一个程序集，并更新该程序集，这些更新或更改不会自动选取您的 BizTalk 项目中。 应在解决方案资源管理器中删除过期的引用，然后重新添加引用 （重新引用程序集）。 或者，可以关闭解决方案并重新打开它。 在任一情况下，引用的程序集最新的更新可供你的项目。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [Microsoft.BizTalk.DefaultPipelines 引用](../core/microsoft-biztalk-defaultpipelines-reference.md)  
  
-   [Microsoft.BizTalk.GlobalPropertySchemas 引用](../core/microsoft-biztalk-globalpropertyschemas-reference.md)  
  
-   [系统引用](../core/system-reference.md)  
  
-   [System.Xml 引用](../core/system-xml-reference.md)