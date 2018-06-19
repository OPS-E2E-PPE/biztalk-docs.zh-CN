---
title: 异常处理服务示例的工作原理 |Microsoft 文档
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
ms.openlocfilehash: eac3a9ff96025f5248c0434a69c38eb01a704488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22293917"
---
# <a name="how-the-exception-handling-service-sample-works"></a>异常处理服务示例的工作原理
异常处理服务示例是一个标准.NET Windows 窗体应用程序包含的异常处理服务生成的服务代理。 该应用程序包含一个按钮，带有的单个窗体**生成异常**。 单击此按钮的实例时**FaultMessage**生成类。 **FaultMessage**类是由基于在 Web 服务描述语言 (WSDL) 提供的异常处理 Web 服务的 Microsoft Visual Studio 生成的类。 此实例的属性填充使用模拟作为参数传递属性之前在外部应用程序中发生的错误的默认值**SubmitFault**异常处理 Web 方法服务。  
  
 有关异常处理 Web 服务的工作原理的详细信息，请参阅[-异常处理的 Web 服务](../esb-toolkit/the-exception-handling-web-service.md)。