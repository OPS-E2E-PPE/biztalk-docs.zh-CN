---
title: 处理外部提交的异常通过自定义处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53fa661e-d391-47c0-92d5-1d0c45b5963d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ec780adcc28318eb76c3dd00aa1f5081323105b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400790"
---
# <a name="handling-externally-submitted-exceptions-using-a-custom-handler"></a>处理外部提交的异常通过自定义处理程序
在此用例，外部客户端将提交一条异常消息通过 Web 服务。 使用 ESB 异常编码器管道组件，预配置的发送端口订阅错误消息;它处理并将其保存为磁盘文件，您可以使用 Microsoft InfoPath 中图 1 所示。  
  
 ![处理外部异常](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3-HandlingExternalExceptions")  
  
 **图 1**  
  
 **处理传入的异常或错误消息并将保存到磁盘文件**  
  
 异常处理服务示例中包含[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何使用 ESB 异常服务作为通用机制来提交，将存储在外部应用程序中的错误消息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]异常管理数据库。 有关详细信息，请参阅[运行异常处理服务示例](../esb-toolkit/running-the-exception-handling-service-sample.md)。