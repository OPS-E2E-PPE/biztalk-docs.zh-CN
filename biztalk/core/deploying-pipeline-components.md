---
title: "部署管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, pipeline components [custom]
- pipeline components [custom], deploying
ms.assetid: 98b47fbf-62c0-4012-a406-58c4d56b305a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 041bd8c6e6fa9c3969be18f0804460c00de5f11a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="deploying-pipeline-components"></a>部署管道组件
所有.NET 管道组件程序集 （本机和自定义） 必须都位于\<*安装目录*\>\Pipeline 组件要由服务器执行的文件夹。 如果将在多台服务器部署管道与自定义组件，组件的二进制文件必须存在的每个服务器上的指定文件夹中。  
  
 不需要添加要由 BizTalk 运行到全局程序集缓存 (GAC) 中使用的自定义管道组件。  
  
 在工具箱中，还将显示在管道中的自定义 COM 组件，提供注册 COM 组件的计算机上。 自定义.NET 管道组件必须放入\<*安装目录*\>\Pipeline 组件文件夹。  
  
 二进制文件位于正确的位置后，你需要将该组件添加到工具箱。 将管道组件添加到工具箱中的说明，请参阅[如何使用工具箱](../core/how-to-use-the-toolbox.md)。  
  
## <a name="see-also"></a>另请参阅  
 [开发自定义管道组件](../core/developing-custom-pipeline-components.md)