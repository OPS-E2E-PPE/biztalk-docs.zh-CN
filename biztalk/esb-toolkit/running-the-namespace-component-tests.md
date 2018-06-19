---
title: 运行 Namespace 组件测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13768608-ade6-44c0-897f-d417c3408302
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ae865e91fd6ff796cb870c71840bde8a95831e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294933"
---
# <a name="running-the-namespace-component-tests"></a>运行 Namespace 组件测试
下面的过程演示如何能够运行的测试方案的所有四个[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]Namespace 组件示例。  
  
 **若要运行示例测试方案的 Namespace 组件**  
  
1.  首次运行此示例之前，请确保，接收位置和发送端口 URL 指向分发源文件中的相应子文件夹。 指定接收位置的子文件夹 \Source\Samples\Namespace\Test\Filedrop\In 和发送端口 URL 子文件夹 \Source\Samples\Namespace\Test\Filedrop\Out。  
  
2.  如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。  
  
3.  创建名为 TEST_Add_to_PassThrough.0000.ns.xml （位于你 ESB 安装文件夹的 \Source\Samples\Namespace\Test\Data\ 子文件夹中），文件副本并删除"TEST_"前缀重命名副本。  
  
4.  将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。  
  
5.  ESB 选取该消息、 将命名空间添加到其中，和到 \Source\Samples\Namespace\Test\Filedrop\Out 子文件夹中将删除该更新的消息。 打开输入和输出中的文本编辑器来查看此测试的影响的文件。  
  
6.  现在运行第二个测试。 创建名为 TEST_Add_to_Remove.0000.ns.xml 文件副本并将其通过删除"TEST_"前缀。  
  
7.  将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。  
  
8.  ESB 选取该消息，向其中添加一个命名空间、 中删除新的命名空间，并将到 \Source\Samples\Namespace\Test\Filedrop\Out 子文件夹中删除该更新的消息。 打开输入和输出中的文本编辑器来查看此测试的影响的文件。  
  
9. 现在运行第三个测试。 创建名为 TEST_PassThrough_to_Remove.0000.ns.xml 文件副本并将其通过删除"TEST_"前缀。  
  
10. 将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。  
  
11. ESB 选取该消息中, 删除现有的命名空间，并将到 \Source\Samples\Namespace\Test\Filedrop\Out 子文件夹中删除该更新的消息。 打开输入和输出中的文本编辑器来查看此测试的影响的文件。  
  
12. 最后，运行第四次测试。 创建名为 TEST_AddViaExtraction_to_PassThrough.0000.ns.xml 文件副本并将其通过删除"TEST_"前缀。  
  
13. 将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。  
  
14. ESB 选取该消息，会在指定的元素中提取**ExtractionNodeXPath**属性，从指定的命名空间值，此元素用于创建一条消息，而到 \Source\Samples\ 删除更新的消息Namespace\Test\Filedrop\Out 子文件夹。 打开输入和输出中的文本编辑器来查看此测试的影响的文件。