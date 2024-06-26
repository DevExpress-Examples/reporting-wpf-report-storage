<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128605188/15.2.4%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T292945)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->
<!-- default file list -->
*Files to look at*:

* [MainWindow.xaml](./CS/WpfApplication38/MainWindow.xaml) (VB: [MainWindow.xaml](./VB/WpfApplication38/MainWindow.xaml))
* [MainWindow.xaml.cs](./CS/WpfApplication38/MainWindow.xaml.cs) (VB: [MainWindow.xaml.vb](./VB/WpfApplication38/MainWindow.xaml.vb))
* [DataSetFileStorage.cs](./CS/WpfApplication38/Storages/DataSetFileStorage.cs) (VB: [DataSetFileStorage.vb](./VB/WpfApplication38/Storages/DataSetFileStorage.vb))
* [StorageDataSet.cs](./CS/WpfApplication38/Storages/StorageDataSet.cs) (VB: [StorageDataSet.vb](./VB/WpfApplication38/Storages/StorageDataSet.vb))
* [StorageEditorForm.xaml](./CS/WpfApplication38/Storages/StorageEditorForm.xaml) (VB: [StorageEditorForm.xaml](./VB/WpfApplication38/Storages/StorageEditorForm.xaml))
* [StorageEditorForm.xaml.cs](./CS/WpfApplication38/Storages/StorageEditorForm.xaml.cs) (VB: [StorageEditorForm.xaml.vb](./VB/WpfApplication38/Storages/StorageEditorForm.xaml.vb))
* [XtraReport1.cs](./CS/WpfApplication38/Storages/XtraReport1.cs) (VB: [XtraReport1.vb](./VB/WpfApplication38/Storages/XtraReport1.vb))
<!-- default file list end -->
# WPF End-User Report Designer - How to Implement a Report Storage


<p>This example demonstrates how to implement report storage to persist <a href="http://documentation.devexpress.com/XtraReports/CustomDocument2592.aspx">report definitions</a> in a database or in any other custom location. This enables your end-users to create and customize reports using the <a href="https://documentation.devexpress.com/#XtraReports/CustomDocument114104">End-User Designer for WPF</a> and have a common target for saving and sharing all reports. This functionality is accomplished through the <strong>DevExpress.Xpf.Reports.UserDesigner.IReportStorage</strong> interface. The interface provides the following methods:</p>
<p>• bool CanCreateNew();</p>
<p>Indicates whether or not it is possible to create a new tab with a blank report in the designer.</p>
<p>• bool CanOpen();</p>
<p>Indicates where or not the "Open" command is available.</p>
<p>• XtraReport CreateNew();</p>
<p>Provides the capability to customize a new report template.</p>
<p>• XtraReport CreateNewSubreport();</p>
<p>Provides the capability to customize a new <a href="https://documentation.devexpress.com/#XtraReports/CustomDocument5175">subreport</a> report template (i.e., a new report opened by double-clicking a specific XRSubreport control).</p>
<p>• string GetErrorMessage(Exception exception);</p>
<p>Provides the capability to display an error message for any encountered exception (a general one or the exception message if you expect that the user can understand and react based on this information).</p>
<p>• string Open(IReportDesignerUI designer);</p>
<p>This method expects a unique ID of the report selected by an end-user via a custom dialog.</p>
<p>• XtraReport Load(string reportID, IReportSerializer designerReportSerializer);</p>
<p>This method passes the report ID that has been selected at the previous step and expects the actual report instance to be loaded and returned. You may or may not use the <strong>IReportSerializer</strong> functionality to save or load a given report from a stream.</p>
<p>• string Save(string reportID, IReportProvider reportProvider, bool saveAs, string reportTitle, IReportDesignerUI designer);</p>
<p>This method is intended to save the currently edited reports. The method's parameters are:</p>
<p>- <em>reportID</em> is a unique ID of the edited report (<strong>null</strong> if it is a new report with no ID specified);</p>
<p>- <em>reportProvider</em> allows you to access the actual report instance being edited and optionally rename it (a new name will be updated in the designer as well);</p>
<p>- <em>saveAs</em> indicates which particular command has been executed ("Save" or "Save As").</p>
<p>- <em>reportTitle</em> represents the actual report title (the <strong>XtraReport.DisplayName</strong> property value).</p>
<p>- <em>designer</em> is the actual report designer instance (a <strong>DevExpress.Xpf.Reports.UserDesigner.ReportDesigner</strong> object).</p>
<p> </p>
<p><strong>See also</strong>: <a href="https://www.devexpress.com/Support/Center/Example/Details/E2704">Report Storage for the WinForms End-User Report Designer</a>.</p>

<br/>


<!-- feedback -->
## Does this example address your development requirements/objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=reporting-wpf-report-storage&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=reporting-wpf-report-storage&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->
