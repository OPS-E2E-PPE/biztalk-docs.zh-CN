---
title: 如何使用选择项目类型对话框 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Select Artifact Type dialog box
- artifacts, Select Artifact Type dialog box
- Orchestration Designer, items
ms.assetid: f0f767f1-4130-4ff0-a898-a089343ee71f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 362f1ffe21023aaddb5b492548914d35348fa5e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333218"
---
# <a name="how-to-use-the-select-artifact-type-dialog-box"></a>如何使用选择项目类型对话框
*项*用于在业务流程设计器中配置业务流程的元素。 项的例子包括架构、 映射、 管道、 端口类型和多部分消息类型。 当开发业务流程，并如端口形状、 转换形状和消息及其组成部分时，可能需要到不位于当前业务流程，但位于当前项目或已编译到的另一个项目中的项，请参阅BizTalk 服务器程序集。 您使用**选择项目类型**对话框找到并配置业务流程中的某个元素时，然后指定项。  
  
 **选择项目类型**从业务流程设计器中的许多位置对话框才可用。 可以选择\<从引用的程序集中\>下拉列表中显示配置选项; 单击此文本会打开**选择项目类型**对话框。  
  
 可以选择一项之前，必须首先选择你想要配置的元素。  
  
 可以使用**选择项目类型**以下特定目的的对话框：  
  
|操作|用途|  
|------------|-------------|  
|选择管道|配置为直接 （早期） 绑定的端口时，请选择用于将管道属性的管道。|  
|选择映射|选择要用于映射**转换**形状。|  
|选择架构|创建多部分消息类型时，请在项目中选择架构。|  
|选择端口类型|创建端口时引用现有端口类型。|  
|选择多部分消息类型|创建消息时引用现有的多部分类型。|  
|选择.NET 类型|创建变量或消息时引用现有的.NET 类型。|  
  
 **引用窗格**  
  
 引用窗格**选择项目类型**对话框中显示的引用在当前项目和其他可用程序集中。 若要在此窗格中选择一个引用，请单击它。 若要展开此窗格中的容器 (如**程序集**容器)，单击其旁边的加号 （+）。  
  
 **项窗格**  
  
 项窗格**选择项目类型**对话框显示当前在引用窗格中选定的引用中包含的项。 项窗格会显示两个列，**项**并**限定名**，随后显示当前引用中的项信息。  
  
### <a name="to-use-the-select-artifact-type-dialog-box"></a>若要使用选择项目类型对话框  
  
1.  展开**引用**的左窗格中的节点。 该窗格显示可用的项目和程序集。  
  
2.  展开**程序集**节点。 列出一个或多个程序集，如系统。DLL 和 MICROSOFT.BIZTALK.PIPELINES.DLL。  
  
3.  单击程序集。 如果该程序集包含项，它们显示在右窗格中。 在右窗格的右侧列中显示项的限定的名称。  
  
    > [!NOTE]
    >  如果当前项目包含项，可以单击它以查看其项并进行选择。  
  
4.  若要在右窗格中选择某个项目，单击它，然后单击**确定**退出**选择项目类型**对话框。 这将会指定该项作为所选元素的类型。 若要关闭**选择项目类型**没有选择并分配一个项，请单击对话框**取消**。  
  
## <a name="see-also"></a>请参阅  
 [业务流程形状](../core/orchestration-shapes.md)   
 [如何向业务流程添加形状](../core/how-to-add-shapes-to-orchestrations.md)   
 [如何将参数添加到业务流程](../core/how-to-add-parameters-to-orchestrations.md)