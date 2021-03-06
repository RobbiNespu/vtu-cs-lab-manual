## Program 4:
### a) Design an XML document to store information about a student in an engineering college affiliated to VTU. The information must include USN, Name, Name of the College, Brach, Year of Joining, and e-mail id. Make up sample data for 3 students. Create a CSS style sheet and use it to display the document.
### b) Create an XSLT style sheet for one student element of the above document and use it to create a display of that element.
***

### Tags used:
     <xsl:stylesheet> - Defines that the document is an XSLT style sheet document (along with the version number and XSLT namespace attributes).
     <xsl:template> - The <xsl:template> element is used to build templates. A template contains rules to apply when a specified node is matched.
     <xsl:for-each> - This element can be used to select every XML element of a specified node-set.
     <xsl:value-of> - This element is used to extract the value of a selected node.

### Code:
*4a.xml*

     <?xml version="1.0" ?>
     	<!-- Obtain stylesheet. Note that the xml file & css file should be in the same directory/location -->
     	<?xml-stylesheet type="text/css" href="4a.css" ?>
     		<student>
     			Student 1 details:
     				<info>
    					USN:<usn>1AB10EC002</usn>
    					Name:<name>abc</name>
    					College:<coll>AB</coll>
    					Branch:<branch>ECE</branch>
    					Year Of Joining:<yoj>2010</yoj>
    					Email-ID:<email>abc@samp.com</email>
    				</info>
    			Student 2 details:
    				<info>
    					USN:<usn>1PQ10CS025</usn>
    					Name:<name>pqr</name>
    					College:<coll>PQ</coll>
    					Branch:<branch>CSE</branch>
    					Year Of Joining:<yoj>2010</yoj>
    					Email-ID:<email>pqr@samp.com</email>
    				</info>
    			Student 3 details:
    				<info>
    					USN:<usn>1XY10IS005</usn>
    					Name:<name>xyz</name>
    					College:<coll>XY</coll>
    					Branch:<branch>ISE</branch>
    					Year Of Joining:<yoj>2010</yoj>
    					Email-ID:<email>xyz@samp.com</email>
    				</info>
    		</student>

*4a.css*

     /* Define styling properties for each tag of the xml file */
     student {margin-top:15px;font-weight:bold;color:black;}
     info {display:block;margin-left:15px;color:gray;}
     usn, name {color:red;font-size:15pt;}
     coll, branch {color:blue;font-size:15pt;}
     yoj, email {color:green;font-size:15pt;}

### Output:
*Steps for checking output-*

* Locate the xml file in the filesystem.
* Make sure that the .xml & .css file are in the same directory.
* `Right-click` on the xml file and select `open-with` firefox/iceweasel/chromium/chrome.
* Observe the output on the browser.

### Code:
*4b.xml*

     <?xml version="1.0" ?>
     <!-- Obtain stylesheet. Note that the xml file & xsl file should be in the same directory/location -->
     <?xml-stylesheet type="text/xsl" href="4b.xsl" ?>
    	<student>
    		<info>
    			<usn>1PQ10CS025</usn>
    			<name>pqr</name>
    			<coll>PQ</coll>
    			<branch>CSE</branch>
    			<yoj>2010</yoj>
    			<email>pqr@samp.com</email>
    		</info>
    	</student>

*4b.xsl*

     <?xml version="1.0"?>
    	<!-- create new namespace instance -->
    	<xsl:stylesheet version="1.0"
    	xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
    		<!-- match all -->
    		<xsl:template match="/">
    			<html>
    				<!-- create table to display -->
    				<table border="1">
    					<tr>
    						<th>USN</th><th>Name</th><th>College</th><th>Branch</th><th>Year Of Joining</th><th>Email-ID</th>
    					</tr>
    					<xsl:for-each select="student/info">
    						<tr>
    							<!-- get each value -->
    							<td><xsl:value-of select="usn" /></td>
    							<td><xsl:value-of select="name" /></td>
    							<td><xsl:value-of select="coll" /></td>
    							<td><xsl:value-of select="branch" /></td>
    							<td><xsl:value-of select="yoj" /></td>
    							<td><xsl:value-of select="email" /></td>
    						</tr>
    					</xsl:for-each>
    				</table>
    			</html>
    		</xsl:template>
    	</xsl:stylesheet>

### Output:
*Steps for checking output-*

* Locate the xml file in the filesystem.
* Make sure that the .xml & .xsl file are in the same directory.
* `Right-click` on the xml file and select `open-with` firefox/iceweasel/chromium/chrome.
* Observe the output on the browser.

### Screenshot:

![output](4.png)
