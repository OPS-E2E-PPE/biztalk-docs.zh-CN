---
title: "运行的异常处理服务示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d69e720c-89e4-42c2-b4d0-31f0b865ab7f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a224c985591801bc9622000c35587b7137f933
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-exception-handling-service-sample"></a>运行的异常处理服务示例
异常处理服务示例演示如何使用异常处理 Web 服务以便提交到 ESB 异常处理框架从外部应用程序的错误。 运行此示例的以下过程需要[安装异常管理示例](../esb-toolkit/installing-the-exception-management-samples.md)。  
  
 **若要运行异常处理服务示例**  
  
1.  在 Windows 资源管理器中打开文件夹 \Source\Samples\ExceptionHandlingService，其中安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后打开名为 ExceptionHandlingService.sln 的 Visual Studio 解决方案文件。  
  
2.  在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，单击**启动调试**工具栏上。  
  
3.  在加载表单中，单击**生成异常**按钮。  
  
4.  在 Windows 资源管理器，依次打开文件夹 \Samples\Exception Handling\Test\Filedrop\All_Exceptions，和最新的 Exceptions_ {GUID}.xml 文件。  
  
5.  检查生成的异常的内容。  
  
 有关如何在异常处理服务示例使用异常管理服务的详细信息，请参阅[异常处理服务示例的工作原理](../esb-toolkit/how-the-exception-handling-service-sample-works.md)。