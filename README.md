<html>
<head>
<script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
  </script>
  <script>    
    
    function swapImages(){
      var $active = $('#myGallery .active');
      var $next = ($('#myGallery .active').next().length > 0) ? $('#myGallery .active').next() : $('#myGallery img:first');
      $next.fadeIn(function(){         
        $active.removeClass('active');
        $next.addClass('active');
        $active.fadeOut();
      })
            
    }
    $(document).ready(function(){
      
      var height = $( window ).height();
      var width = $( window ).width();
      var size = width + ',' + height;
      
      var locations = [        
        /*** EDIT THIS SECTION ***
 
        Put the links to your viz here, make sure to include the following url parameters
        &:embed=yes&:toolbar=no&:format=png&<filter/parameter>=<value>
        to make sure it auto sizes add this to the url as well &:size="+size+"
        Example:
      
        {"src": "https://public.tableausoftware.com/views/Animated-Map/map?:showVizHome=no&:embed=yes&:toolbar=no&:format=png&Year=2010"},            
        ** with add'l years **
        {"src": "https://public.tableausoftware.com/views/Animated-Map/map?:showVizHome=no&:embed=yes&:toolbar=no&:format=png&Year=2011"},
        {"src": "https://public.tableausoftware.com/views/Animated-Map/map?:showVizHome=no&:embed=yes&:toolbar=no&:format=png&Year=2012"},
        {"src": "https://public.tableausoftware.com/views/Animated-Map/map?:showVizHome=no&:embed=yes&:toolbar=no&:format=png&Year=2013"},
        */
        {"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Cardiology"}, 
        {"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Cardiothoracic%20Surgery"}, 
        {"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Dermatology"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=ENT"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Gastroenterology"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=General%20Medicine"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=General%20Surgery"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Geriatric%20Medicine"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Gynaecology"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Neurology"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Neurosurgery"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Ophthalmology"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Oral%20Surgery"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Other"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Plastic%20Surgery"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Rheumatology"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Thoracic%20Medicine"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Trauma%20%26%20Orthopaedics"}, 
	{"src": "https://public.tableau.com/views/EnglandRTTPerformanceByMonth-EnglandBySpecialtyWIP/WaitingListBySpecialtySinceRTTRecordsBegan?:embed=y&:showVizHome=no&:toolbar=no&:format=png&Treatment%20Function=Urology"}, 
        
                ]
            
      $("#myGallery").attr('width',width);
      $("#myGallery").attr('height',height);
      
      var img = '';
      
      locations.forEach(function(element, index, array){
        
        
        if(index==0){         
          img = '<img src="'+locations[index].src+'" class="active" />';
        } else {
          img = '<img src="'+locations[index].src+'" />';         
        }
        console.log('index: '+index+' == '+img);    
        
        $(img).appendTo("#myGallery");
        
      })
      
      
      // Change 3000 to whatever time interval you prefer
      setInterval('swapImages()', 3000);
    });
  </script>
  <style>
    
    body {
      background-color: #353535;
    }
    #myGallery{
      position:relative;
    }
    #myGallery img{
      display:none;
      position:absolute;
      top:0;
      left:0;
    }
    #myGallery img.active{
      display:block;
    }
  </style>
</head>
<body>
  <div id="myGallery">
  </div>
</body>
</html>
