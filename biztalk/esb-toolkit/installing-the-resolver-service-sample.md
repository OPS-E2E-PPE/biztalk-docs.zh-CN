---
title: "安装解析程序服务示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fce9bbeb-9377-41af-8ca7-740ce4d1f617
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bd438725b53362cda1b041af697283e68d77ba7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="installing-the-resolver-service-sample"></a>安装解析程序服务示例
本部分介绍安装解析程序服务示例的过程。 解析程序服务依赖于[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心解决方案。 安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心自动将复制和安装此示例为正确的位置所需的核心程序集。  
  
 **若要从解决方案项目安装解析程序服务示例**  
  
1.  在 Windows 资源管理器，打开 \Source\Samples\ResolverService\Install\Scripts 文件夹。  
  
2.  双击 Setup_bin.cmd 文件。  
  
3.  若要确认成功安装了此示例中，或者如果当你运行应用程序时遇到问题，可以使用下表中提供的列表来检查是否存在所需的程序集和其他项目。  
  
|位置|类别|名称和版本的组件|  
|--------------|--------------|---------------------------------------|  
|BizTalk 应用程序 GlobalBank.ESB|业务流程|（无）|  
|BizTalk 应用程序 GlobalBank.ESB|发送端口|（无）|  
|BizTalk 应用程序 GlobalBank.ESB|接收端口|（无）|  
|BizTalk 应用程序 GlobalBank.ESB|接收位置|（无）|  
|BizTalk 应用程序 GlobalBank.ESB|架构|（无）|  
|BizTalk 应用程序 GlobalBank.ESB|管道|（无）|  
|BizTalk 应用程序 GlobalBank.ESB|Resources|（无）|  
|BizTalk 应用程序 GlobalBank.ESB|策略|ResolveEndpoint|  
|||ResolveMap|  
|BizTalk 应用程序 GlobalBank.ESB|地图|（无）|  
|全局程序集缓存|程序集|（无）|  
|%Program 文件 %\\BizTalk Server\Pipeline 组件|管道组件|（无）|