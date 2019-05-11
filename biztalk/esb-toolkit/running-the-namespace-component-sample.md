---
title: 运行 Namespace 组件示例 |Microsoft Docs
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
ms.openlocfilehash: 31a7ced4587f693c13f3fd45f24057eb882f1d43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242719"
---
# <a name="running-the-namespace-component-sample"></a>运行 Namespace 组件示例
Namespace 组件示例应用程序包含四个接收位置 / 发送端口对。 每一对表示一个测试。 以下是四种测试：  

- **将添加到直通**。 此测试将命名空间添加到 XML 消息文档和消息将直接写入到一个文件，以便您可以看到新的命名空间。 此测试的输入的文件是 TEST_Add_to_PassThrough.0000.ns.xml。 此测试使用**NamespaceSampleReceivePipeline** ，其中包含**AddNamespace**组件。  

- **将添加到删除**。 此测试将命名空间添加到的 XML 文档的消息，并将其删除。 它然后将消息直接写入一个文件。 此测试的输入的文件是 TEST_ Add_to_Remove.0000.ns.xml。 此测试使用**NamespaceSampleReceivePipeline** ，其中包含**AddNamespace**组件并**NamespaceSampleSendPipeline** ，其中包含**RemoveNamespace**组件。  

- **传递到删除**。 此测试从 XML 文档消息中删除所有命名空间和消息将直接写入到一个文件，以便你可以确认这一点。 此测试的输入的文件是 TEST_PassThrough_to_Remove.0000.ns.xml。 此测试使用**NamespaceSampleSendPipeline** ，其中包含**RemoveNamespace**组件。  

- **添加通过提取到直通**。 此测试中提取**OrderDetails**元素的 XML 文档的消息并将事件写入包含文件直接将此元素的新消息。 此测试的输入的文件是 TEST_AddViaExtraction_to_PassThrough.0000.ns.xml。 此测试使用**NamespaceSampleReceivePipeline** ，其中包含**AddNamespace**组件与**ExtractionNodeXPath**属性设置为 **/CanonicalOrder/OrderDetails** （任何有效的 XPath，返回对应的元素为此属性就足够了）。  

  在示例应用程序的基础的接收位置具有适用于每个测试类型的文件掩码和相关的接收端口名称在发送端口筛选器。 因此，若要执行测试，您只需相应地命名的消息放入输入文件夹。 示例应用程序执行测试，并将更新后的消息放入输出文件夹使用适用于当前测试的名称，并包括消息 id。  

  本节包含下列主题：  

- [运行命名空间组件测试](../esb-toolkit/running-the-namespace-component-tests.md)  

- [添加命名空间示例工作原理](../esb-toolkit/how-the-add-namespace-sample-works.md)  

- [删除命名空间示例工作原理](../esb-toolkit/how-the-remove-namespace-sample-works.md)
