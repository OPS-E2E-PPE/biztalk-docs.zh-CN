---
title: "步骤 3： 实现 Echo 适配器的连接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc223901-3ad3-4e71-8672-fea6bb4efe65
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a735654fd03f5efb39fe73eb845f4db3632d283
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-implement-the-connection-for-the-echo-adapter"></a>步骤 3： 实现 Echo 适配器的连接
![步骤 3 中 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")  
  
 **完成时间：** 45 分钟  
  
 在此步骤中，你可以实现 Echo 适配器的连接功能。 根据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，连接到目标系统时，则必须实现以下的抽象类和接口。  
  
-   `Microsoft.ServiceModel.Channels.Common.ConnectionUri`  
  
-   `Microsoft.ServiceModel.Channels.Common.IConnection`  
  
-   `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`  
  
 而不是派生自上述抽象类和接口，[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成三个派生的类、 EchoAdapterConnection、 EchoAdapterConnectionUri 和 EchoAdapterConnectionFactory。 除了创建类，每个已引发特定异常的默认方法`System.NotImplementedException`。  此语句提醒开发人员实现每个类。  实现类时，必须删除此异常引发的语句。  
  
 在以下部分中，你将更新这些 3 个类来更好地理解如何处理连接、 URI 结构是什么，以及如何以编程方式检索各种 URI 元素，然后使用这些元素置于该适配器。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，你必须已成功完成[步骤 2： 对适配器和连接属性进行分类](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)。 并且你应拥有清楚地了解`Microsoft.ServiceModel.Channels.Common.IConnection`， `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`，和`Microsoft.ServiceModel.Channels.Common.ConnectionUri`类。  
  
## <a name="connection-related-classes"></a>连接相关的类  
 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]生成三个派生的类、 EchoAdapterConnection、 EchoAdapterConnectionUri 和 EchoAdapterConnectionFactory。 下面提供与每个关联方法的简要概述。  
  
### <a name="echoadapterconnection"></a>EchoAdapterConnection  
 根据你适配器复杂性，你可能需要实施所有以下五个方法。 对于 Echo 适配器，大多数不支持，因为 Echo 适配器示例不涉及任何目标系统。  
  
|**方法**|**Description**|  
|----------------|---------------------|  
|公共 void 关闭 （TimeSpan 超时）|关闭到目标系统的连接。 Echo 适配器使用此方法仅将跟踪事件添加到跟踪侦听器。|  
|公共 bool IsValid （TimeSpan 超时）|返回一个值，该值指示连接是否仍有效。<br /><br /> 不支持 Echo 适配器。|  
|公共 void 打开 （TimeSpan 超时）|打开连接到目标系统。<br /><br /> Echo 适配器的不适用。 但是，该示例显示您如何使用 URI 元素调用 enableAuthentication 来要求用户提供的用户名。|  
|公共 void ClearContext()|清除连接的上下文。 返回到连接池设置的连接时，调用此方法。<br /><br /> 不支持 Echo 适配器。|  
|公共 void abort （)|中止连接到目标系统。<br /><br /> 不支持 Echo 适配器。|  
  
### <a name="echoadapterconnectionfactory"></a>EchoAdapterConnectionFactory  
 连接工厂负责创建连接。 仅在连接到目标系统时，默认情况下，你必须修改此类。 尽管 Echo 适配器不涉及任何目标系统，它演示如何使用自定义 URI 元素调用 enableAuthentication，如果你的连接需要用户身份验证。  
  
> [!NOTE]
>  EnableAuthentication 不是一个关键字，它是只是变量的名称。 因此，您可以选择为其任何名称。  
  
### <a name="echoadapterconnectionuri"></a>EchoAdapterConnectionUri  
 这表示到目标系统的连接字符串。  
  
|**方法**|**Description**|  
|----------------|---------------------|  
|公共重写 Uri Uri|获取和设置的 Uri。 获取生成的 Uri 字符串和设置要分析的 Uri 字符串。|  
|公共 EchoAdapterConnectionUri()|初始化 ConnectionUri 类的新实例。|  
|公共重写字符串 SampleUriString|返回 EchoAdapter.SCHEME +": //{hostname}/{application}?enableAuthentication={True &#124;False}"。<br /><br /> 此返回的字符串将显示为**示例**中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具，如下图中所示。|  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")  
  
## <a name="echo-adapter-connection-uri"></a>Echo 适配器连接 URI  
 示例 Echo 适配器连接 URI 被描述为： EchoAapter.SCHEME://{hostname}/{application}?enableAuthentication={true &#124; 否则为 false}  
  
 由于 EchoAapter.SCHEME 是 echov2，连接 URI 为着：  
  
 echo2: / lobhostname/lobapplication？ enableAuthentication = {true &#124; 否则为 false}  
  
 你可以阅读前一连接 URI 时 enableAuthentication = false，如下所示：  
  
 使用 echov2 传输架构，转到名为 lobhostname 的计算机名为不需要任何身份验证的 lobapplication 应用程序正在等待你的连接。  
  
 或者，当 enableAuthentication = true，读取连接，如下所示：  
  
 使用 echov2 传输架构，转到名为 lobhostname 的计算机名为 lobapplication 应用程序需要身份验证正在等待你的连接。 对于 Echo 适配器中，仅包含用户名称是必需的。  
  
 具有定义的 URI，可以以编程方式使用和分析的连接和配置。 如果连接需要用户名和密码等敏感数据，不包含 URI 中的此类信息。 相反，请添加中的此类信息`System.ServiceModel.Description.ClientCredentials`对象。 你添加的代码示例演示如何执行此操作。  
  
 在下面的代码中，Echo 适配器构造以两种方式显示该适配器可以如何使用各种 URI 元素来修改适配器功能的 URI。  
  
 echo2: / lobhostname/lobapplication？ enableAuthentication = [true &#124; 否则为 false]  
  
 echo2: / lobhostname/lobapplication？ enableAuthentication = [true &#124; 否则为 false] & echoInUpperCase = true  
  
### <a name="retrieving-the-uri-element"></a>在检索 URI 元素  
 你可以分析每个 URI 元素中的 Echo 适配器 URI echo2: / lobhostname/lobapplication？ enableAuthentication = false echoInUpperCase = false。  下表中列出了 URI 的元素值和关联的方法：  
  
|**URI 元素值**|**方法**|  
|---------------------------|----------------|  
|lobhostname|`System.Uri.Host%2A`若要检索的主机名|  
|Lobapplication|`System.Uri.AbsolutePath%2A`若要检索的目标应用程序名称|  
|enableAuthentation = false|GetQueryStringValue("enableAuthentication")<br /><br /> 使用此 URI 元素来验证用户凭据**注意：** GetQueryStringValue 是中定义的静态方法`Microsoft.ServiceModel.Channels.Common.ConnectionUri`|  
|echoInUpperValue = false|GetQueryStringValue("echoInUpperValue")<br /><br /> 使用此 URI 元素将传入的字符串转换为大写形式。|  
  
### <a name="enableauthentication-uri-element"></a>EnableAuthentication URI 元素  
 目标系统通常要求你提供用于建立到目标系统的连接的客户端凭据。 如前文所述，Echo 适配器不涉及任何目标系统。 作为示例，但它演示如何使用自定义 URI 元素调用 enableAuthentication 提供的凭据。  
  
```  
 public class EchoAdapterConnection : IConnection   
{  
….  
   public void Open(TimeSpan timeout)  
  {  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
  }  
}  
```  
  
 代码将检查是否 enableAuthentication 是 true，如果未提供的用户名;如果未提供的用户名称，它将引发异常，由捕获[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具，如下所示：  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/901095c7-c70d-491a-a1ae-8f37f22a61a7.gif "901095c7-c70d-491a-a1ae-8f37f22a61a7")  
  
 若要提供的用户名，则可以输入它在配置适配器对话框中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具，如下图中所示：  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4069a7d-1403-4195-b0b5-21ad97dbc3ce.gif "e4069a7d-1403-4195-b0b5-21ad97dbc3ce")  
  
### <a name="echoinuppercase-uri-element"></a>EchoInUpperCase URI 元素  
 可以像一个布尔型标志一样引用 EchoInUpperCase URI 元素。 如果标志为 true，该适配器将 EchoStrings 操作的输入的字符串转换为大写形式中。  
  
 若要更改 echoInUpperCase URI 元素的默认值，使用中的配置适配器的 URI 属性选项卡[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如下所示。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f22511b2-3fca-4875-ac65-8e61f4367e94.gif "f22511b2-3fca-4875-ac65-8e61f4367e94")  
  
## <a name="updating-echoadapterconnection"></a>更新 EchoAdapterConnection  
 实现 EchoAdapterConnection 类的 IsValid、 打开和关闭方法。  
  
#### <a name="to-update-the-echoadapterconnection-class"></a>若要更新 EchoAdapterConnection 类  
  
1.  在**解决方案资源管理器**，双击**EchoAdapterConnection.cs**文件。  
  
2.  在 Visual Studio 编辑器中，右键单击任意位置在编辑器中，在上下文菜单中，依次指向**大纲**，然后单击**停止大纲显示**。  
  
3.  在 Visual Studio 编辑器中，查找**IsValid**方法。 内部**IsValid**方法，将现有实现替换所示：  
  
    ```csharp  
    return true;  
    ```  
  
4.  在 Visual Studio 编辑器中，查找**打开**方法。 内部**打开**方法，将现有实现替换为以下实现。 这将向你展示如何使用 URI enableAuthentication 元素以确保提供的用户名：  
  
    ```csharp  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        // it just logs the credentials in the trace file  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
        // got the username, log it in trace file  
        EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Username is " + this.connectionFactory.ClientCredentials.UserName.UserName);  
    }  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully established!");  
    ```  
  
5.  在 Visual Studio 编辑器中，查找**关闭**方法。 内部**关闭**方法，添加下面的单个语句：  
  
    ```csharp  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Close", "Connection successfully closed!");  
    ```  
  
## <a name="updating-the-echoadapterconnectionfactory"></a>更新 EchoAdapterConnectionFactory  
 实现 EchoAdapterConnectionFactory 构造函数，并添加称为 ClientCredentials 和 ConnectionUri 的两个属性。  
  
#### <a name="to-update-the-echoadapterconnectionfactory-class"></a>若要更新 EchoAdapterConnectionFactory 类  
  
1.  在**解决方案资源管理器**，双击**EchoAdapterConnectionFactory.cs**文件。  
  
2.  在 Visual Studio 编辑器中，右键单击任意位置在编辑器中，在上下文菜单中，依次指向**大纲**，然后单击**停止大纲显示**。  
  
3.  在 Visual Studio 编辑器中，查找**私有字段**区域。 添加下面的单个语句：  
  
    ```csharp  
    private EchoAdapterConnectionUri connectionUri;  
    ```  
  
     你的私有字段的列表应该匹配以下项：  
  
    ```csharp  
    // Stores the client credentials  
    private ClientCredentials clientCredentials;  
    // Stores the adapter class  
    private EchoAdapter adapter;  
    private EchoAdapterConnectionUri connectionUri;  
    ```  
  
4.  在 Visual Studio 编辑器中，查找**EchoAdapterConnectionFactory**方法。 内部**EchoAdapterConnectionFactory**构造函数方法之前"}"，添加下面的单个语句作为最后一条语句。  
  
    ```csharp  
    this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    ```  
  
     实现**EchoAdapterConnectionFactory**方法应匹配以下内容：  
  
    ```csharp  
    /// <summary>  
    /// Initializes a new instance of the EchoAdapterConnectionFactory class  
    /// </summary>  
    public EchoAdapterConnectionFactory(ConnectionUri connectionUri  
        , ClientCredentials clientCredentials  
        , EchoAdapter adapter)  
    {  
        this.clientCredentials = clientCredentials;  
        this.adapter = adapter;  
        //added  
        this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    }  
    ```  
  
5.  在 Visual Studio 编辑器中，查找**公共属性**区域。 添加以下代码：  
  
    ```csharp  
    /// <summary>  
    /// Returns the client credentials  
    /// </summary>  
    public ClientCredentials ClientCredentials  
    {  
        get  
        {  
            return this.clientCredentials;  
        }  
    }  
  
    /// <summary>  
    /// Returns the Connection Uri for this adapter  
    /// </summary>  
    public EchoAdapterConnectionUri ConnectionUri  
    {  
        get  
        {  
            return this.connectionUri;  
        }  
    }  
    ```  
  
## <a name="updating-the-echoadapterconnectionuri"></a>更新 EchoAdapterConnectionUri  
 实现 EchoAdapterConnectionUri 默认构造函数、 EchoAdapterConnectionUri(Uri uri) 重载构造函数和公共重写 Uri Uri 属性。  
  
#### <a name="to-update-the-echoadapterconnectionuri-class"></a>若要更新 EchoAdapterConnectionUri 类  
  
1.  在**解决方案资源管理器**，双击**EchoAdapterConnectionUri.cs**文件。  
  
2.  在 Visual Studio 编辑器中，右键单击任意位置在编辑器中，在上下文菜单中，依次指向**大纲**，然后单击**停止大纲显示**。  
  
3.  在 Visual Studio 编辑器中，查找**构造函数**区域。 内部**EchoAdapterConnectionUri()**默认构造函数中，添加以下语句：  
  
    ```csharp  
    Uri = new Uri("echov2://lobhostname/lobapplication?enableauthentication=False");  
    ```  
  
4.  在 Visual Studio 编辑器中，内部**EchoAdapterConnectionUri (Uri uri)**重载构造函数，并添加以下语句：  
  
    ```csharp  
    Uri = uri;  
    ```  
  
     EchoAdapterConnectionUri(Uri uri) 方法的实现应匹配以下项：  
  
    ```csharp  
    public EchoAdapterConnectionUri(Uri uri)  
        : base()  
    {  
        Uri = uri;  
    }  
    ```  
  
5.  在 Visual Studio 编辑器中，内部**公共重写 Uri Uri**方法，将现有具有以下逻辑。 Get 生成 echoInUpperCase 带有或不带它的 Uri。 集分析的 URI 来检索主机名、 数据库名称和查询值。  
  
    ```csharp  
    get  
    {  
        // Build the uri  
        if (String.IsNullOrEmpty(this.hostname)) throw new InvalidUriException("Invalid target system host name.");  
        if (String.IsNullOrEmpty(this.application)) throw new InvalidUriException("Invalid target system data source name.");  
        if (EchoInUpperCase)  
        {  
            // build the uri with echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication + "&" + "echoInUpperCase=" + echoInUpperCase);  
        }  
        else  
        {  
            // build the uri without echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication);  
        }  
    }  
    set  
    {  
        // Parse the uri  
        String[] enableAuthValue = GetQueryStringValue(value, "enableAuthentication");  
        if (enableAuthValue.Length > 0) this.enableAuthentication = Boolean.Parse(enableAuthValue[0]);  
        String[] echoInUpperValue = GetQueryStringValue(value, "echoInUpperCase");  
        if (echoInUpperValue.Length > 0) this.echoInUpperCase = Boolean.Parse(echoInUpperValue[0]);  
  
        this.hostname = value.Host;  
        String[] applicationValue = value.AbsolutePath.Split('/');  
        if (applicationValue.Length > 1) this.Application = applicationValue[1];  
    }  
    ```  
  
6.  在 Visual Studio 中，在**文件**菜单上，单击**保存所有**。  
  
7.  在“生成”  菜单上，单击“生成解决方案” 。 你应已成功编译该项目。 如果没有，请确保您已按照上述每个步骤。  
  
> [!NOTE]
>  保存所做的工作。 你可以安全地在此时关闭 Visual Studio 或转到下一步，[步骤 4： 为 Echo 适配器实现的元数据浏览处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)。  
  
## <a name="what-did-i-just-do"></a>未我只需做什么？  
 实现 Echo 适配器的连接。 你已了解的连接组件[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、 连接 URI 的基本结构、 如何以编程方式分析 URI 元素中，以及如何使用 URI 元素更改适配器功能。  
  
## <a name="next-steps"></a>后续步骤  
 你实现元数据浏览、 搜索和解析功能和出站消息交换。 最后，生成并部署该适配器。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4： 为 Echo 适配器实现元数据浏览的处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)   
 [教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)