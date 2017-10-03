---
title: "前期和后期处理脚本用于自定义应用程序部署 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- customizing, applications
- applications, customizing
- scripts, applications
- scripts, customizing
ms.assetid: 47627394-d594-491b-9098-38c5d028a378
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dc0afd7ed042f475a9a008125c968f401e6df92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-pre--and-post-processing-scripts-to-customize-application-deployment"></a>前期和后期处理脚本用于自定义应用程序部署
本部分中的各个主题描述如何创建预处理脚本或后处理脚本来在导入、安装或卸载应用程序时执行操作。 预处理脚本在应用程序导入或安装开始前以及卸载完成后执行某一个或某一组操作。 后处理脚本在应用程序导入或安装完成后、或者在卸载开始前执行某一个或某一组操作。  
  
 例如，您可能要包括一个预处理脚本，该脚本将在安装前运行，以便在安装期间资源文件被覆盖前备份它们。 或者，您可能要运行一个后处理脚本，以便在安装某一应用程序后将某个证书添加到证书存储。  
  
> [!NOTE]
>  BizTalk Server 包括预处理脚本和后处理脚本的示例。 有关使用示例脚本的信息，请参阅[模板 （应用程序部署示例）](../core/template-application-deployment-sample.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建预或后续处理脚本](../core/creating-a-pre-or-post-processing-script.md)  
  
-   [环境变量如何指示部署状态](../core/how-environment-variables-indicate-deployment-state.md)  
  
-   [在部署过程中的文件项目的状态](../core/status-of-file-artifacts-during-deployment.md)  
  
-   [前期和后期处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md)