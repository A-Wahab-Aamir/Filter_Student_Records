# Filter_Student_Records
    <script>
      function displayData() {
        for (var i = 0; i < data.length; i = i + 1) {
          document.getElementById("table_body").innerHTML += `
                <tr>
                    <td>${i}</td>
                        <td>${data[i].Name}</td>
                        <td>${data[i].f_Name}</td>
                        <td>${data[i].class}</td>
                        <td>${data[i].contact}</td>
                        <td><img src="${data[i].profile}" alt="" id='img'></td>
                </tr>
                
                `;
          document.getElementById("select").innerHTML += `
                 <option value="${i}">${i} </option>
                
                `;
        }
      }
      function filterData(index) {
        if (index === "all") {
            document.getElementById("table_body").innerHTML = "";
          document.getElementById(
            "select"
          ).innerHTML = `<option value='all'>Select All Students!</option>`;
          displayData();
        } else {
          let dataToMap = [data[index]];
          for (var i = 0; i < dataToMap.length; i = i + 1) {
            document.getElementById("table_body").innerHTML = `
                  <tr>
                      <td>${index}</td>
                          <td>${dataToMap[i].Name}</td>
                          <td>${dataToMap[i].f_Name}</td>
                          <td>${dataToMap[i].class}</td>
                          <td>${dataToMap[i].contact}</td>
                          <td><img src="${dataToMap[i].profile}" alt="" id='img'></td>
                  </tr>
                  `;
          }
        }
      }

      displayData();
    </script>
