<template>
  <!-- #D1D8F7 -->
  <p class="header-text">Upcoming movie premieres</p>
  <p class="subheader-text">Keep track of the upcoming movie premieres</p>
  <div class="table-container">
    <table class="custom-table">
      <thead>
        <tr>
          <th class="name-header">
            <div class="name-header-content">
              <input type="checkbox" />
              <span>Name</span>
              <img
                src="https://i.postimg.cc/wjXBNJJP/Vector.png"
                alt="Down Arrow"
                class="down-arrow"
              />
            </div>
          </th>
          <th>Category</th>
          <th>Watchlists</th>
          <th>Owner</th>
          <th>Premier Date</th>
          <th>Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in tableData" :key="index">
          <td class="name-cell">
            <img :src="item.image" alt="User Image" class="user-img" />
            <span>{{ item.name }}</span>
          </td>
          <td class="category-cell">
            <button class="action-btn">{{ item.category1 }}</button>
            <button class="action-btn">{{ item.category2 }}</button>
          </td>
          <td>{{ item.watchlists }}</td>
          <td>{{ item.owner }}</td>
          <td>{{ item.premierDate }}</td>
          <td class="action-cell">
            <button class="view-btn">View</button>
          </td>
        </tr>
      </tbody>
      <!-- Footer Section inside the table -->
      <!-- <tfoot>
          <tr>
            <td colspan="6" class="footer">
              <button style="width: 230px; height: 45px;" class="footer-btn">View all upcoming premieres</button>
            </td>
          </tr>
        </tfoot> -->

      <tfoot>
        <tr>
          <td colspan="6" class="footer">
            <div class="footer-btn-container">
              <button style="width: 230px; height: 45px" class="footer-btn">
                View all upcoming premieres
              </button>
            </div>
          </td>
        </tr>
      </tfoot>
    </table>
  </div>
</template>

<script setup>
const tableData = [
  {
    name: "John Doe",
    image: "https://i.postimg.cc/xC3mDy89/unsplash-PXj-Qa-Gxi4-JA.png",
    category1: "Edit",
    category2: "Delete",
    watchlists: 123,
    owner: "Admin",
    premierDate: "2025-04-01",
  },
  {
    name: "Jane Smith",
    image: "https://i.postimg.cc/fyfHX8zy/unsplash-h-Puna2k4-PXE.png",
    category1: "Edit",
    category2: "Delete",
    watchlists: 89,
    owner: "Editor",
    premierDate: "2025-03-27",
  },
  {
    name: "John Doe",
    image: "https://i.postimg.cc/3Rg95tD1/unsplash-h-Puna2k4-PXE.png",
    category1: "Edit",
    category2: "Delete",
    watchlists: 123,
    owner: "Admin",
    premierDate: "2025-04-01",
  },
  {
    name: "Jane Smith",
    image: "https://i.postimg.cc/ZnHc00Hy/download.png",
    category1: "Edit",
    category2: "Delete",
    watchlists: 89,
    owner: "Editor",
    premierDate: "2025-03-27",
  },
];
</script>

<style>
/* Apply Helvetica Neue font to the entire page */
* {
  font-family: "Helvetica Neue", Arial, sans-serif;
}

/* Centering the text */
.header-text,
.subheader-text {
  font-weight: 400;
  font-size: 14px;
  text-align: center;
  margin-right: 870px;
}

.header-text {
  margin-bottom: 8px;
}

.subheader-text {
  margin-top: 0;
}

.table-container {
  padding: 0 24px;
  margin: 40px auto;
  max-width: 1200px;
  overflow-x: auto;
}

.custom-table {
  width: 100%;
  border-collapse: collapse;
  font-family: "Helvetica Neue", Arial, sans-serif;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  overflow: hidden;
  background-color: white;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
}

.custom-table thead {
  background-color: #f5f5f6;
}

.custom-table th,
.custom-table td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #e0e0e0;
}

.custom-table th:last-child,
.custom-table td:last-child {
  border-right: none;
}

.custom-table tr:last-child td {
  border-bottom: none;
}

.name-header {
  min-width: 160px;
}

.name-header-content {
  display: flex;
  align-items: center;
  gap: 8px;
  justify-content: flex-start;
  position: relative;
}

.name-header-content .down-arrow {
  margin-left: 8px;
  width: 16px;
  height: 16px;
}

.name-cell {
  display: flex;
  align-items: center;
  gap: 10px;
}

.user-img {
  width: 30px;
  height: 30px;
  border-radius: 50%;
}

.action-btn {
  margin-right: 5px;
  padding: 2px 12px;
  border: none;
  background-color: #d1d8f7;
  color: #4755ab;
  border-radius: 6px;
  font-weight: 500;
  cursor: pointer;
}

.action-btn:hover {
  background-color: #c5cefa;
}

/* Aligning the "View" button to the right and making it smaller */
.action-cell {
  text-align: right;
}

.view-btn {
  padding: 6px 12px; /* Adjusted padding for smaller button */
  border: 1px solid #ccc;
  background-color: white;
  color: #333;
  border-radius: 6px;
  font-weight: 500;
  cursor: pointer;
}

.view-btn:hover {
  background-color: #f0f0f0;
}

/* Footer styles inside table */
.footer {
  background-color: #f5f5f6; /* Same color as the header */
  text-align: center;
  padding: 0;
}

.footer-btn {
  width: 100%;
  padding: 12px;
  background-color: #ffffff;
  color: black;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-weight: 500;
  font-size: 13px; 
  transition: background-color 0.3s ease, color 0.3s ease;
}

.footer-btn:hover {
  background-color: #3c47a0;
  color: white; 
}

.footer-btn-container {
  text-align: right; /* Aligns the button to the right */
}


.footer-btn:hover {
  background-color: #3c47a0;
}
</style>
