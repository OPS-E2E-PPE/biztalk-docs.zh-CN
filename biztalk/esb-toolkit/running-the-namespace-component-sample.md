---
title: 运行 Namespace 组件示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f334a8-06de-4a56-a41a-3df088bf4a72
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fc142ca70971f023e491dbdeee693a8d41c42fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295293"
---
# <a name="running-the-namespace-component-sample"></a>运行 Namespace 组件示例
Namespace 组件示例应用程序包含四个接收位置/发送端口对。 每个对表示一个测试。 以下是四种测试：  
  
-   **将添加到传递**。 此测试将命名空间添加到 XML 消息文档，并将消息直接写入文件，以便你可以看到新的命名空间。 此测试的输入的文件是 TEST_Add_to_PassThrough.0000.ns.xml。 此测试使用**NamespaceSampleReceivePipeline**包含**AddNamespace**组件。  
  
-   **将添加到删除**。 此测试将命名空间添加为 XML 文档消息，并将其删除。 它然后将消息直接写入文件。 此测试的输入的文件是 TEST_ Add_to_Remove.0000.ns.xml。 此测试使用**NamespaceSampleReceivePipeline**包含**AddNamespace**组件和**NamespaceSampleSendPipeline**包含**RemoveNamespace**组件。  
  
-   **传递到删除**。 此测试从 XML 文档消息中移除所有命名空间，并将消息直接写入文件，以便你可以对此进行确认。 此测试的输入的文件是 TEST_PassThrough_to_Remove.0000.ns.xml。 此测试使用**NamespaceSampleSendPipeline**包含**RemoveNamespace**组件。  
  
-   **通过传递到提取添加**。 此测试中提取**OrderDetails**元素的 XML 文档的消息和写入新消息包含此元素直接到文件。 此测试的输入的文件是 TEST_AddViaExtraction_to_PassThrough.0000.ns.xml。 此测试使用**NamespaceSampleReceivePipeline**包含**AddNamespace**组件**ExtractionNodeXPath**属性设置为 **/CanonicalOrder/OrderDetails** （任何有效的 XPath，它返回元素。 此属性就足够了）。  
  
 在示例应用程序的基础接收位置具有文件掩码适用于每个测试类型中，并相关，则将发送端口筛选器上的接收端口名称。 因此，若要执行测试，你只需放在适当命名的消息的输入的文件夹。 示例应用程序执行测试并将更新的消息放置到输出文件夹中使用适用于当前的测试，名称且包括消息 id。  
  
 本节包含下列主题：  
  
-   [运行 Namespace 组件测试](../esb-toolkit/running-the-namespace-component-tests.md)  
  
-   [如何添加 Namespace 示例的工作机制](../esb-toolkit/how-the-add-namespace-sample-works.md)  
  
-   [删除 Namespace 示例的工作原理](../esb-toolkit/how-the-remove-namespace-sample-works.md)