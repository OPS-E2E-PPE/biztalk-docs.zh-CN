---
title: 处理外部提交使用自定义处理的异常 |Microsoft 文档
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
ms.openlocfilehash: 7ba3fc49756619f77188f0a311ff46eb18e7f0b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294053"
---
# <a name="handling-externally-submitted-exceptions-using-a-custom-handler"></a>处理外部提交使用自定义处理的异常
在使用此种情况下，外部客户端将提交一条异常消息通过 Web 服务。 发送端口，预先配置为使用 ESB 异常编码器管道组件，订阅的错误消息;它处理，并将其保存为磁盘文件，以便你可以查看使用 Microsoft InfoPath 中图 1 所示。  
  
 ![处理外部异常](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3 HandlingExternalExceptions")  
  
 **图 1**  
  
 **处理传入的异常或错误消息并将保存到磁盘文件**  
  
 在异常处理服务示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何使用作为通用机制 ESB 异常服务提交从外部应用程序将存储在错误消息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]异常管理数据库。 有关详细信息，请参阅[运行异常处理服务示例](../esb-toolkit/running-the-exception-handling-service-sample.md)。