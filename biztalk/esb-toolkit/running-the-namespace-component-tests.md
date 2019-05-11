---
title: 运行 Namespace 组件测试 |Microsoft Docs
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
ms.openlocfilehash: 7e60a4ee44d80747bdeb50ac199c2d5354482abb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242704"
---
# <a name="running-the-namespace-component-tests"></a>运行 Namespace 组件测试
下面的过程演示如何运行的测试方案的所有四个[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]Namespace 组件示例。  
  
 **若要运行示例测试方案的 Namespace 组件**  
  
1.  第一次运行此示例之前，请确保该接收位置和发送端口 URL 指向分发源文件中的相应子文件夹。 指定接收位置的子文件夹 \Source\Samples\Namespace\Test\Filedrop\In 和发送端口 URL 子文件夹 \Source\Samples\Namespace\Test\Filedrop\Out。  
  
2.  如果尚未运行 GlobalBank.ESB 应用程序，使用 Microsoft BizTalk 管理控制台来启动它。  
  
3.  制作一份名为 TEST_Add_to_PassThrough.0000.ns.xml （位于 \Source\Samples\Namespace\Test\Data\ ESB 安装文件夹的子文件夹中），该文件并删除"TEST_"前缀重命名副本。  
  
4.  将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。  
  
5.  ESB 提取该消息，将命名空间添加到它，并将更新后的消息放入 \Source\Samples\Namespace\Test\Filedrop\Out 子文件夹。 打开输入和输出文件中的文本编辑器来查看此测试的效果。  
  
6.  现在，运行第二个测试。 创建名为 TEST_Add_to_Remove.0000.ns.xml 文件的副本并重命名通过删除"TEST_"前缀。  
  
7.  将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。  
  
8.  ESB 提取该消息，向其添加一个命名空间、 删除新命名空间，并将更新后的消息放入 \Source\Samples\Namespace\Test\Filedrop\Out 子文件夹。 打开输入和输出文件中的文本编辑器来查看此测试的效果。  
  
9. 现在，运行第三个测试。 创建名为 TEST_PassThrough_to_Remove.0000.ns.xml 文件的副本并重命名通过删除"TEST_"前缀。  
  
10. 将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。  
  
11. ESB 提取该消息，删除现有命名空间，并将更新后的消息放入 \Source\Samples\Namespace\Test\Filedrop\Out 子文件夹。 打开输入和输出文件中的文本编辑器来查看此测试的效果。  
  
12. 最后，运行第四次测试。 创建名为 TEST_AddViaExtraction_to_PassThrough.0000.ns.xml 文件的副本并重命名通过删除"TEST_"前缀。  
  
13. 将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。  
  
14. ESB 提取该消息，提取中指定的元素**ExtractionNodeXPath**属性，此元素与指定的命名空间值，从创建一条消息，并将更新后的消息放入 \Source\Samples\Namespace\Test\Filedrop\Out 子文件夹。 打开输入和输出文件中的文本编辑器来查看此测试的效果。