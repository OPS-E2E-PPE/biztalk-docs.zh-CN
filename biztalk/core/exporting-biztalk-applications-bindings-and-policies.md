---
title: 导出 BizTalk 应用程序、 绑定和策略 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, exporting
- exporting, policies
- bindings, exporting
- exporting, applications
- applications, exporting
- exporting, bindings
ms.assetid: ac101206-be49-47c9-a354-4f39e8b77acf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d6df445b0fefc132940a736870d66c62329ce60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245805"
---
# <a name="exporting-biztalk-applications-bindings-and-policies"></a>导出 BizTalk 应用程序、绑定和策略
本部分介绍如何导出 BizTalk 应用程序、绑定或策略。 可以导出在某一 BizTalk 应用程序中包含的某些或所有项目，也可以只导出该应用程序的绑定或策略。 导出 BizTalk 应用程序会创建一个 Windows Installer (.msi) 文件，该文件包含您选择导出的应用程序项目。 导出绑定或策略将创建一个包含这些绑定或策略的 .xml 文件。 此过程的背景信息，请参阅[什么发生时项目导出](../core/what-happens-when-artifacts-are-exported.md)。  
  
 您可以将某一应用程序 .msi 文件导入其他 BizTalk 组，以便在该组中创建包含该应用程序项目的新应用程序。 您可以将某一绑定或策略 .xml 文件导入其他 BizTalk 应用程序，以便使用这些绑定或策略。 中介绍了如何导入项目[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)。  
  
> [!IMPORTANT]
>  请将绑定文件存储于安全的位置，因为它们可能包含连接和配置信息之类的重要业务数据。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)  
  
-   [导出绑定](../core/exporting-bindings6.md)  
  
-   [如何导出策略](../core/how-to-export-a-policy.md)