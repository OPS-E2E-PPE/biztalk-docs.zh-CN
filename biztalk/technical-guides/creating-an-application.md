---
title: 创建应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b6e325c-a86f-419d-9a27-864f4f035507
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 772ba15d357715d5ceeca3c229167a96f7ef6c60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987542"
---
# <a name="creating-an-application"></a>创建应用程序
有三种方法来创建 BizTalk 应用程序。 也有几个选项为命名、 引用，并将项目部署到应用程序。  
  
## <a name="creating-a-biztalk-application"></a>创建 BizTalk 应用程序  
 通过三种方式是按如下所示：  
  
1. 使用 BizTalk Server 管理控制台的 New Application 命令或 BTSTask 命令行工具的 AddApp 命令来创建 BizTalk 应用程序。 有关使用这些命令的详细信息，请参阅[如何创建应用程序](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)。  
  
2. 导入从另一个应用程序导出的 .msi 文件。 如果该应用程序在当前 BizTalk 组中不存在，则在当前 BizTalk 组中自动创建该应用程序，包括其项目。 有关导入应用程序的详细信息，请参阅[导入 BizTalk 应用程序的方式](http://go.microsoft.com/fwlink/?LinkID=154827)(http://go.microsoft.com/fwlink/?LinkID=154827)。  
  
3. 将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序。 如果 Visual Studio 中的项目的部署属性中指定的应用程序不存在当前的 BizTalk 组中，它将自动创建。 部署 Visual Studio 中的程序集的详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。  
  
   若要部署使用某一.msi 文件的应用程序，该目标应用程序不需要存在，但将自动创建。 但是，若要导入绑定到另一个应用程序中，目标应用程序必须已存在。 如果没有，您需要通过执行上面列出的过程之一来创建。  
  
   有关创建应用程序所需的特定步骤的详细信息，请参阅[如何创建应用程序](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)。  
  
## <a name="application-options"></a>应用程序选项  
 在创建新的应用程序之前, 应执行以下操作：  
  
-   确定在应用程序的 BizTalk 组中是唯一的名称。  
  
-   添加新应用程序中对任何应用程序包含你想要在新的应用程序中重复使用的项目的引用。 有关应用程序之间的依赖关系的详细信息，请参阅[依赖项和应用程序部署](http://go.microsoft.com/fwlink/?LinkId=155008)(http://go.microsoft.com/fwlink/?LinkId=155008)。  
  
-   确定您是否要将某些项目部署到单独的应用程序，例如，应部署到其自己单独的应用程序的共享项目。