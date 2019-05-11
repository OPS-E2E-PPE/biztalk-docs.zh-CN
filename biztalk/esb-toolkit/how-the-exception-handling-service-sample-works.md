---
title: 异常处理服务示例的工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d095752-e212-42bf-9559-efa14d2ad09c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 254d7a5b5cbf2e431ff7db4309774d8315367e2d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400786"
---
# <a name="how-the-exception-handling-service-sample-works"></a>异常处理服务示例的工作原理
异常处理服务示例是一个包含异常处理服务生成的服务代理的标准.NET Windows 窗体应用程序。 此应用程序包含一个按钮，使用一个窗体**生成异常**。 当单击此按钮的实例**FaultMessage**生成类。 **FaultMessage**类是由 Microsoft Visual Studio 基于在 Web 服务描述语言 (WSDL) 提供的异常处理 Web 服务生成的类。 此实例的属性使用模拟之前属性作为参数传递到外部应用程序中发生的错误的默认值填充**SubmitFault**异常处理 Web 方法服务。  
  
 有关异常处理 Web 服务的工作原理的详细信息，请参阅[，异常处理 Web 服务](../esb-toolkit/the-exception-handling-web-service.md)。