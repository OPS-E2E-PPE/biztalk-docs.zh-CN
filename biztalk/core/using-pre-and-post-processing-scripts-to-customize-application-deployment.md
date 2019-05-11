---
title: 使用预处理和后处理脚本自定义应用程序部署 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- customizing, applications
- applications, customizing
- scripts, applications
- scripts, customizing
ms.assetid: 47627394-d594-491b-9098-38c5d028a378
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23734f43a479e4e526535b61f0e9b957752e03d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396572"
---
# <a name="using-pre--and-post-processing-scripts-to-customize-application-deployment"></a>使用预处理和后处理脚本自定义应用程序部署
在本部分中的主题介绍如何创建预处理或后处理脚本来执行的操作导入应用程序时，安装或卸载。 应用程序导入或安装开始前以及卸载完成后，预处理脚本执行的操作或组的操作。 应用程序导入或安装完成后，或在卸载开始前，后续处理脚本执行一个操作或一组操作。  
  
 例如，可能想要包括在安装之前安装过程中覆盖备份资源文件前将运行的预处理脚本。 或者，可能想要运行一个后处理脚本来安装应用程序后，将证书添加到证书存储区。  
  
> [!NOTE]
>  BizTalk Server 包含示例预处理和后处理脚本。 有关使用示例脚本的信息，请参阅[模板 （应用程序部署示例）](../core/template-application-deployment-sample.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建预处理脚本或后期处理脚本](../core/creating-a-pre-or-post-processing-script.md)  
  
-   [环境变量如何指示部署状态](../core/how-environment-variables-indicate-deployment-state.md)  
  
-   [部署过程中的文件项目状态](../core/status-of-file-artifacts-during-deployment.md)  
  
-   [预处理脚本和后期处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md)