---
title: 部署管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, pipeline components [custom]
- pipeline components [custom], deploying
ms.assetid: 98b47fbf-62c0-4012-a406-58c4d56b305a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14ac8f8c91b0ed8b83a6bcbcf4664726c0079515
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389583"
---
# <a name="deploying-pipeline-components"></a>部署管道组件
所有.NET 管道组件程序集 （本机和自定义） 必须都位于\<*安装目录*\>\Pipeline Components 文件夹中，由服务器执行。 如果具有自定义组件的管道将部署在多台服务器，该组件的二进制文件必须存在的每个服务器上指定的文件夹中。  
  
 不需要添加用于 BizTalk 运行时到全局程序集缓存 (GAC) 中使用的自定义管道组件。  
  
 在工具箱中，还将显示在管道中的自定义 COM 组件，提供注册 COM 组件的计算机上。 自定义.NET 管道组件必须放入\<*安装目录*\>\Pipeline Components 文件夹。  
  
 二进制文件都位于正确的位置后，需要将组件添加到工具箱。 有关向工具箱添加管道组件的说明，请参阅[如何使用工具箱](../core/how-to-use-the-toolbox.md)。  
  
## <a name="see-also"></a>请参阅  
 [开发自定义管道组件](../core/developing-custom-pipeline-components.md)