---
title: "将适配器设置公开为使用 WCF LOB 适配器 SDK 绑定属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59728113-917e-4bca-8e1a-609cd6558944
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c72ba43378829c71bfb3379bb70ea274de652c9b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk"></a>将适配器设置公开为使用 WCF LOB 适配器 SDK 绑定属性
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]使用在配置连接池、 元数据缓存和其他适配器行为的不同类中定义的属性。 本主题介绍如何为绑定属性，图面这些属性，以便适配器使用者可以通过配置文件设置它们。  
  
### <a name="to-surface-an-adapter-setting-as-an-adapter-binding-property"></a>展示为适配器绑定属性的适配器设置  
  
1.  启动 Visual Studio，然后在**文件**菜单上，指向**新建**，然后单击**项目**。  
  
2.  选择**WCF LOB 适配器**模板，然后提供的其他适配器项目信息。  
  
3.  单步执行[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]。 当你到达**适配器属性**页上，添加你想要通过提供公开的绑定属性**属性名称**，**数据类型**，和**默认值**，然后单击**添加**以添加新的适配器属性。  
  
4.  完成[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]。 你的项目应包含由向导提供的新文件。  
  
5.  在 Visual Studio 中，在解决方案资源管理器，打开适配器派生类。 例如，如果适配器项目的名称是"SampleAdapter"，可以在"SampleAdapter.cs"中找到的适配器派生类。  
  
6.  删除你想要获取和设置从适配器设置的属性的私有变量。 生成的私有变量[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]。  
  
7.  更新 get/set 方法为读/写从/到适配器设置的值。 下面的示例使用适配器属性来允许启用的性能计数器。  
  
    ```  
    [System.Configuration.ConfigurationProperty("enablePerfCounters", DefaultValue = false)]  
    public bool EnablePerfCounters  
    {  
        get { return environmentSettings.PerformanceCounters.Enabled;    }  
        set { environmentSettings.PerformanceCounters.Enabled = value; }  
    }  
    ```  
  
8.  在 Visual Studio 中，在**文件**菜单上，单击**保存所有**。  
  
## <a name="see-also"></a>另请参阅  
 [教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)[开发活动](../../esb-toolkit/development-activities.md)