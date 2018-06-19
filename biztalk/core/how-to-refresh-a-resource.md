---
title: 如何刷新资源 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [resources], refreshing
- refreshing resources
- resources, refreshing
ms.assetid: d6ff7c9d-8aaf-42a4-b1a3-00c05f6ac869
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bee05b9f137bbec92eccfa217084b66f1e5bf8ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254541"
---
# <a name="how-to-refresh-a-resource"></a>如何刷新资源
本主题介绍如何使用 BizTalk Server 管理控制台来刷新资源项目。 一种方法是更新 BizTalk 管理数据库中的项目信息。 另一种方法执行此操作是通过将项目添加到应用程序使用 BTSTask [AddResource 命令](../core/addresource-command.md)使用覆盖选项。  
  
 资源项目包含在应用程序的“资源”文件夹中。 如果对源文件进行了更改，并要用更新后的文件替换应用程序中的文件，则要刷新资源项目  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-refresh-a-resource-artifact"></a>刷新资源项目  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开包含资源项目的 BizTalk 组若要刷新，，然后展开包含该项目的应用程序。  
  
3.  单击**资源**文件夹，右键单击该文件以刷新，，然后单击**修改**。  
  
4.  在**修改资源**对话框中，选择要刷新的文件，然后单击**刷新**。  
  
5.  浏览到你想要替换当前的文件中，更新文件，然后单击**确定**。  
  
     当前文件将替换为该已更新文件。 在添加、 配置、 设置显示在**选项**选项卡**修改资源**对话框中应用于刷新的文件。 有关更改这些设置的详细信息，请单击**帮助**在对话框中。  
  
## <a name="see-also"></a>另请参阅  
 [管理前期和后期处理脚本](../core/managing-pre-and-post-processing-scripts.md)   
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [管理资源](../core/managing-resources.md)