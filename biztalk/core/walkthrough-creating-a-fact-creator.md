---
title: 演练：创建事实创建器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041c8f73-c72e-43fd-8446-144cecdc95ef
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d159428f3e9b2c303a9e4df69d1df616aaabf5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250176"
---
# <a name="walkthrough-creating-a-fact-creator"></a>演练：创建事实创建器
本演练提供了创建事实创建器组件的分步过程**POFactCreator**，这可用于测试**ProcessPurchaseOrder**先前在创建的策略演练。  

## <a name="prerequisites"></a>先决条件  
 必须完成[演练：创建简单业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练在执行本演练之前。  

## <a name="overview-of-this-walkthrough"></a>本演练概述  
 本演练包含两个过程，如下表中所述。  

|过程标题|过程说明|  
|---------------------|---------------------------|  
|创建 POFactCreator 组件|提供创建事实创建器组件的分步说明**POFactCreator**。|  
|若要测试使用 POFactCreator ProcessPurchaseOrder 策略|提供使用业务规则编辑器工具来测试的分步说明**ProcessPurchaseOrder**通过使用策略**POFactCreator**组件。|  

### <a name="to-create-the-pofactcreator-component"></a>创建 POFactCreator 组件  

1. 启动**Microsoft Visual Studio**。  

2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。  

3. 在中**新的项目**对话框框中，执行以下操作：  


   |             使用此选项              |                             执行的操作                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         **项目类型**         |                        单击**Visual C#**。                         |
   |           **模板**           |                      单击**类库**。                       |
   |             **名称**              |                     类型**POFactCreatorLib**。                      |
   |           **位置**            |          指定**C:\BRE-Walkthroughs**作为位置。           |
   |         **解决方案名称**         |                     类型**POFactCreatorSol**。                      |
   | **创建解决方案的目录** | 选中此复选框以创建解决方案文件的目录。 |


4. 单击“确定” 。 **POFactCreatorLib**项目应该显示在解决方案资源管理器。 如果看不到解决方案资源管理器，请单击**解决方案资源管理器**上**视图**菜单。  

5. 在属性窗口中更改文件的名称**Class1.cs**给**POFactCreator.cs**。  

6. 在解决方案资源管理器窗口中，右键单击**引用**，然后单击**添加引用**。  

7. 单击**浏览**，导航到**C:\Program Files\Common Files\Microsoft BizTalk**，然后双击**Microsoft.RuleEngine.dll**。  

8. 将以下行添加到顶部**POFactCreator.cs**之后的现有文件`using`语句：  

   ```  
   //To use the XmlDocument class  
   using System.Xml;  
   //To use the TypedXmlDocument and Policy classes  
   using Microsoft.RuleEngine;   
   ```  

9. 修改**POFactCreator**类进行派生**IFactCreator**接口：  

    ```  
    public class POFactCreator : IFactCreator  
    {  
    }  
    ```  

10. 右键单击**IFactCreator**，依次指向**实现接口**，然后单击**实现接口**。  

     ![BRE&#45;演练&#45;ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")  

11. 添加到一个公共构造函数**POFactCreator**类，如下所示：  

    ```  
    public POFactCreator()  
    {  
    }  
    ```  

12. 删除中的单个语句**CreateFacts**方法。  

13. 将以下代码添加到**CreateFacts**方法来创建**TypedXmlDocument**对象基于**SamplePO.xml**文档：  

    ```  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    ```  

14. 添加以下代码以创建一个与事实数组**TypedXmlDocument**对象作为其唯一事实：  

    ```  
    object[] facts = new object[1];  
    facts[0] = txd;   
    ```  

15. 返回事实数组**CreateFacts**方法：  

    ```  
    return facts;  
    ```  

16. 验证中的完整代码**CreateFacts**方法看起来如下所示：  

    ```  
    public object[] CreateFacts(RuleSetInfo ruleSetInfo)  
    {  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  

    object[] facts = new object[1];  
    facts[0] = txd;  
    return facts;  
    }  
    ```  

17. 删除中的单个语句**GetFactTypes**方法。  

18. 将以下代码添加到**GetFactTypes**方法以返回一个类型包含的类型的数组**TypedXmlDocument**类：  

    ```  
    Type[] t = new Type[1];  
    t[0] = typeof(TypedXmlDocument);  
    return t;  
    ```  

19. 启动**Visual Studio 命令提示符**。  

20. 将目录更改为**C:\BRE-Walkthroughs\POFactCreatorSol**，然后执行以下命令：  

     **Sn -k POFactCreator.snk**  

21. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，展开**属性**，然后双击**AssemblyInfo.cs**。  

22. 添加以下语句到**AssemblyInfo.cs**文件的末尾：  

    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreator.snk")]  
    ```  

23. 在解决方案资源管理器窗口中，右键单击**POFactCreatorLib**，然后单击**生成**。  

24. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改为**C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**，然后执行以下命令以注册**POFactCreator**组件向 GAC （全局程序集缓存）。 如果没有命令提示符下打开，请按照步骤 19，以将其打开。  

     **Gacutil -i POFactCreatorLib.dll**  

### <a name="to-test-the-processpurchaseorder-policy-using-pofactcreator"></a>若要测试使用 POFactCreator ProcessPurchaseOrder 策略  

1. 上**启动**菜单，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则编辑器**。 如果你有业务规则编辑器已打开，请按 f5 键刷新。  

   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  

2. 在策略浏览器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击最新版本，然后单击**测试策略**。  

    ![业务规则编辑器&#45;TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")  

3. 在对话框的底部，单击**添加**。  

4. 在中 **.NET 程序集**对话框中，选择**POFactCreatorLib**，然后单击**确定**。  

5. 在中**选择绑定**对话框中，单击**POFactCreator**中**POFactCreatorLib，10.0.0**，然后单击**确定**。  

6. 单击**测试**。  

7. 确认**ApprovalRule**激发输出窗口中。  

## <a name="comments"></a>注释  

-   若要测试的策略，通过使用业务规则编辑器将使用.NET 类的非静态方法，必须创建事实创建器组件。  

## <a name="see-also"></a>请参阅  
 [如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)