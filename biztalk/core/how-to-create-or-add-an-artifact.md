---
title: 如何创建或添加项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, creating
- applications, artifacts
ms.assetid: fea7487c-b5fa-457f-8c74-a20ea3a6df85
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b231cdf6a25c4ca316c9620ee789e6e3a715fd6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249485"
---
# <a name="how-to-create-or-add-an-artifact"></a>如何创建或添加项目
创建 BizTalk 应用程序后，可以从文件系统中添加基于文件的项目（例如，BizTalk 程序集、.NET 程序集、脚本和证书），或者可以从规则引擎数据库中添加策略。 您也可以在应用程序中创建发送端口、发送端口组、接收位置和接收端口。 创建或添加项目可将其添加到 BizTalk 管理数据库中。 你可以随后部署应用程序和其项目作为单个实体中所述[部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)。  
  
> [!NOTE]
>  在 BizTalk 应用程序或组中，某些项目类型必须是唯一的。 有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。  
  
 有关添加或创建每一项目类型的过程，请参阅以下主题：  
  
-   [如何创建发送端口](../core/how-to-create-a-send-port2.md)  
  
-   [如何创建发送端口组](../core/how-to-create-a-send-port-group.md)  
  
-   [如何创建接收端口](../core/how-to-create-a-receive-port.md)  
  
-   [如何创建接收位置](../core/how-to-create-a-receive-location.md)  
  
-   [如何将策略添加到应用程序](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [如何将一个预或后续处理脚本添加到应用程序](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [如何将文件添加到应用程序](../core/how-to-add-a-file-to-an-application.md)  
  
-   [如何将证书添加到应用程序](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [如何将 COM 组件添加到应用程序](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [如何将.NET 程序集添加到应用程序](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [如何将一个 BAM 项目添加到应用程序](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
> [!NOTE]
>  如果要添加的项目具有很长的路径（例如，路径和文件名），则将项目添加到应用程序的操作可能会失败。 路径不能超过 260 个字符。  
  
## <a name="see-also"></a>另请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)   
 [如何将一个 64 位项目添加到应用程序](../core/how-to-add-a-64-bit-artifact-to-an-application.md)