# me
name: Update TryHackMe Badge

on:
  schedule:
    - cron: '0 0 * * *' # Runs every day at midnight
  workflow_dispatch: # Allows manual triggering

jobs:
  update-badge:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout repository
      uses: actions/checkout@v2
    - name: Fetch TryHackMe Badge
      uses: ./
      with:
        image_path: './assets/tryhackme-badge.png'
        username: 'dhanushnehru'
        user_id: '1995656'
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }} 
